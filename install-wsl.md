# Installing WSL

0. Make sure you have the latest Windows version (for WSL2)

    To use WSL 2, you must be running Windows 11 or in Windows 10:

    * For x64 systems: Version 1903 or later, with Build 18362 or later.
    * For ARM64 systems: Version 2004 or later, with Build 19041 or later.

1. Enable the Windows Subsystem for Linux

    Run the following command in PowerShell as Administrator.

    ```powershell
    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
    ```

1. Enable Virtual Machine feature

    Run the following command in PowerShell as Administrator.

    ```powershell
    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
    ```

1. Install Linux Kernel update package ([link](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi))

1. Restart machine
1. Set WSL 2 as your default version running `wsl --set-default-version 2` in PowerShell/cmd
1. Install your Linux distribution of choice from Microsoft Store (eg.: Ubuntu)
1. Launch the distribution for setup
1. Run `wsl` from a terminal and you should be inside your WSL instance

Check [this](/setup-xserver.md) for running WSL GUI Apps on Windows.