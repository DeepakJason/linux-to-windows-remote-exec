# Linux to Windows

## ❌ PSExec

PSExec cannot be installed on Linux

## ✅ OpenSSH

Same steps [as outlined in this document](./windows-to-windows.md#✅-openssh)

## ❔ Powershell remoting over WSMan/WinRM

WSMan / WinRM is not natively supported on Linux.

Source machine prerequisites:

- @TODO

Target machine prerequisites:

- Enable PowerShell remoting by running the `Enable-PSRemoting` cmdlet.
- Configure the WinRM service by running the `winrm quickconfig` command or `Set-WSManQuickConfig` cmdlet.

## ✅ Powershell remoting over OpenSSH

Same steps [as outlined in this document](./windows-to-windows.md#✅-powershell-remoting-over-openssh)

## ❔ Mimicing PSExec

Target machine prerequisites:

- The `File and Printer Sharing for Microsoft Networks` feature must be enabled. This will expose the `admin$` share.
