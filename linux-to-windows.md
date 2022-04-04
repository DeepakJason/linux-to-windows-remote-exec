# Linux to Windows

## ❌ PSExec

PSExec cannot be installed on Linux

## ✅ OpenSSH

Source machine prerequisites:

- Install the OpenSSH server by following the [steps outlined in this document](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse#install-openssh-using-powershell).

Target machine prerequisites:

- None required. Just connect to the target machine using SSH as follows: `ssh username@targetip`. You'll get prompted for password.

## ❔ Powershell remoting over WSMan/WinRM

WSMan / WinRM is not natively supported on Linux.

Source machine prerequisites:

- @TODO

Target machine prerequisites:

- Enable PowerShell remoting by running the `Enable-PSRemoting` cmdlet.
- Configure the WinRM service by running the `winrm quickconfig` command or `Set-WSManQuickConfig` cmdlet.

## ❔ Powershell remoting over OpenSSH

Source machine prerequisites:

Target machine prerequisites:

## ❔ Mimicing PSExec

Target machine prerequisites:

- The `File and Printer Sharing for Microsoft Networks` feature must be enabled. This will expose the `admin$` share.
