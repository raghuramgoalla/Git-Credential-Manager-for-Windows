## Git Credential Manager for Windows: Configuration Options


### Git Configuration Options


 **authority**

  > Defines the type of authentication to be used.

  > Supports Auto, Basic, AAD, MSA, and Integrated.

  > Defaults to _Auto_.

  `git config --global credential.microsoft.visualstudio.com.authority AAD`


 **httpProxy**

  > Causes the proxy value to be considered when evaluating credential target information. A proxy setting should established if use of a proxy is required to interact with Git remotes.

  > The value should the URL of the proxy server.

  `git config --global credential.github.com.useHttpPath https://myproxy:8080`


 **interactive**

  > Specifies if user can be prompted for credentials or not.

  > Supports Auto, Always, or Never. Defaults to Auto.

  > Only used by AAD, MSA, and GitHub authority.

  `git config --global credential.microsoft.visualstudio.com.interactive never`


 **modalPrompt**

  > Forces authentication to use a modal dialog instead of asking for credentials at the command prompt.

  > Defaults to _true_.

  `git config --global credential.modalPrompt true`


 **namespace**

  > Sets the namespace for stored credentials.

  > By default the GCM uses the 'git' namespace for all stored credentials, setting this configuration value allows for control of the namespace used globally, or per host.

  `git config --global credential.namespace name`


 **preserve**

  > Prevents the deletion of credentials even when they are reported as invalid by Git. Can lead to lockout situations once credentials expire and until those credentials are manually removed.

  > Defaults to _false_.

  `git config --global credential.visualstudio.com.preserve true`


 **useHttpPath**

  > Causes the path portion of the target URI to considered meaningful.

  > By default the path portion of the target URI is ignore, if this is set to true the path is considered meaningful and credentials will be store for each path.

  > Defaults to _false_.

  `git config --global credential.bitbucket.com.useHttpPath true`


 **validate**

  > Causes validation of credentials before supplying them to Git. Invalid credentials get a refresh attempt before failing. Incurs some minor overhead.

  > Defaults to _true_. Ignored by _Basic_ authority.

  `git config --global credential.microsoft.visualstudio.com.validate false`


 **writelog**

  > Enables trace logging of all activities. Logs are written to the local .git/ folder at the root of the repository.

  > Defaults to _false_.

  `git config --global credential.writelog true`


###Sample Configuration###
```INI
[credential "microsoft.visualstudio.com"]
    authority = AAD
    interactive = never
    validate = false
[credential "visualstudio.com"]
    authority = MSA
[credential]
    helper = manager
    writelog = true
```
