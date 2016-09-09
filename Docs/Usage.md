# Git Credential Manager for Windows

## Usage and Commands

 Generally speaking, Git will use the Git Credential Manager for Windows [GCM] and you will only need to interact with any authentication dialogs asking for credentials. As much as possible, the GCM attempts to stay out of sight and out of mind. We believe that the GCM is doing its best job when you forget you're depending on it at all.

### Usage

  Using your favorite Windows console (Command Prompt, PowerShell, ConEmu, etc) use the following command to directly interact with the GCM.

 `git credential-manager [<command> [<args>]]`

### Commands

 **delete**

 Removes stored credentials for a given URL. Any future attempts to authenticate with the remote will require authentication steps to be completed again.


 **deploy _[--path \<installion_path\>] [--passive] [--force]_**

 Deploys the Git Credential Manager for Windows package and sets Git configuration to use the helper.


   *--path \<installion_path\>*

   > Specifies a path (\<installion_path\>) for the installer to deploy to. If a path is provided, the installer will not seek additional Git installations to modify.


   *--passive*

   > Instructs the installer to not prompt the user for input during deployment and restricts output to error messages only.

   > When combined with *--force* all output is eliminated; only the return code can be used to validate success.


   *--force*

   > Instructs the installer to proceed with deployment even if prerequisites are not met or errors are encountered.

   > When combined with *--passive* all output is eliminated; only the return code can be used to validate success.


 **remove _[--path \<installion_path\>] [--passive] [--force]_**

 Removes the Git Credential Manager for Windows package and unsets Git configuration to no longer use the helper.


   *--path \<installion_path\>*

   > Specifies a path (\<installion_path\>) for the installer to remove from. If a path is provided, the installer will not seek additional Git installations to modify.


   *--passive*

   > Instructs the installer to not prompt the user for input during removal and restricts output to error messages only.

   > When combined with *--force* all output is eliminated; only the return code can be used to validate success.


   *--force*

   > Instructs the installer to proceed with removal even if prerequisites are not met or errors are encountered.

   > When combined with *--passive* all output is eliminated; only the return code can be used to validate success.


 **version**

 Displays the current version.


 **clear**

 Synonym for **delete**.


 **install**

 Synonym for **deploy**.


 **uninstall**

 Synonym for **remove**.
 