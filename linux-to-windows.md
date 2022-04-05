# Linux to Windows

## ❌ PSExec

PSExec cannot be installed on Linux

## ✅ OpenSSH

Same steps [as outlined in this document](./windows-to-windows.md#✅-openssh)

## ❔ Powershell remoting over WSMan/WinRM

WSMan / WinRM is not natively supported on Linux.

Target machine prerequisites:

- Enable PowerShell remoting by running the `Enable-PSRemoting` cmdlet.
- Configure the WinRM service by running the `winrm quickconfig` command or `Set-WSManQuickConfig` cmdlet.

Source machine prerequisites:

- @TODO

## ✅ Powershell remoting over OpenSSH

Same steps [as outlined in this document](./windows-to-windows.md#✅-powershell-remoting-over-openssh)

## ❔ Mimicing PSExec

Target machine prerequisites:

- The `File and Printer Sharing for Microsoft Networks` feature must be enabled. This will expose the `admin$` share.

Source machine prerequisites:

- Mount the target's `admin$` share as follows:
  - `sudo mkdir /mnt/win_share`
  - `sudo mount -t cifs -o username=ADMIN-USERNAME-OF-REMOTE-TARGET-MACHINE //IP-OF-REMOTE-TARGET-MACHINE/admin$ /mnt/win_share`
  - More details in [this document](https://linuxize.com/post/how-to-mount-cifs-windows-share-on-linux/).
- @TODO
- Configuring Windows services on target machine:
  - ❌ PowerShell: Unfortunately, on linux, PowerShell 7 does not include cmdlets for:
    - Managing services (like `Start-Service`, `Set-Service` etc).
    - WMI services (like `Get-WmiObject`, `Get-CimInstance` etc).
  - Can PSExecSvc.exe be extracted and installed as a service remotely?
  - Use WMI?
  - Use .NET core?
