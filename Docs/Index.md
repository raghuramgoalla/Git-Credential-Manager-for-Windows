# Git Credential Manager for Windows

The [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows) (GCM) provides secure Git credential storage for Windows. It's the successor to the [Windows Credential Store for Git](https://gitcredentialstore.codeplex.com/) (git-credential-winstore), which is no longer maintained. Compared to Git's built-in credential storage for Windows ([wincred](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage)), which provides single-factor authentication support working on any HTTP enabled Git repository, GCM provides multi-factor authentication support for [Visual Studio Team Services](https://www.visualstudio.com/), [Team Foundation Server](#q-i-thought-microsoft-was-maintaining-this-why-does-the-gcm-not-work-as-expected-with-tfs), and GitHub.

This project includes:

* Secure password storage in the Windows Credential Store
* Multi-factor authentication support for Visual Studio Team Services
* Two-factor authentication support for GitHub
* Personal Access Token generation and usage support for Visual Studio Team Services and GitHub
* Non-interactive mode support for Visual Studio Team Services backed by Azure Directory
* Kerberos authentication for Team Foundation Server ([see notes](#q-i-thought-microsoft-was-maintaining-this-why-does-the-gcm-not-work-as-expected-with-tfs))
* Optional settings for build agent optimization

This is a community project so feel free to contribute ideas, submit bugs, fix bugs, or code new features. For detailed information on how the GCM works go to the [wiki](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/wiki/How-the-Git-Credential-Managers-works).

## Download and Install

To use the GCM, you can download the [latest installer](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). To install, double-click Setup.exe and follow the instructions presented.

When prompted to select your terminal emulator for Git Bash you should choose the Windows' default console window. GCM cannot prompt you for credentials in a MinTTY setup.

## How to use

You don't. It [magically](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/issues/31) works when credentials are needed. For example, when pushing to [Visual Studio Team Services](https://www.visualstudio.com), it automatically opens a window and initializes an oauth2 flow to get your token.

### Manual Installation

Note for users with special installation needs, you can still extract the `gcm-<version>.zip` file and run install.cmd from an administrator command prompt. This allows specification of the installation options explained below.

### Build and Install from Sources

To build and install the GCM yourself, clone the sources, open the solution file in Visual Studio, and build the solution. All necessary components will be copied from the build output locations into a `.\Deploy` folder at the root of the solution. From an elevated command prompt in the `.\Deploy` folder issue the following command `git-credential-manager install`.

Various options are available for uniquely configured systems, like automated build systems. For systems with a **non-standard placement of Git** use the `--path <git>` parameter to supply where Git is located and thus where the GCM should be deployed to. For systems looking to **avoid checking for the Microsoft .NET Framework** and other similar prerequisites use the `--force` option. For systems looking for **silent installation without any prompts**, use the `--passive` option.

