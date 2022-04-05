
# Misc

## How to copy files from Linux to Windows over SMB

Target machine prerequisites:

- The `File and Printer Sharing for Microsoft Networks` feature must be enabled. This will expose the `admin$` share.

Source machine prerequisites:

- Mount the target's `admin$` share as follows:
  - `sudo mkdir /mnt/win_share`
  - `sudo mount -t cifs -o username=ADMIN-USERNAME-OF-REMOTE-TARGET-MACHINE //IP-OF-REMOTE-TARGET-MACHINE/admin$ /mnt/win_share`
  - More details in [this document](https://linuxize.com/post/how-to-mount-cifs-windows-share-on-linux/).

## Other Misc Notes

- The `-ComputerName` options is no longer available in some PS cmdlets (starting with PS 7 onwards).
- Difference between `-ComputerName` vs `-HostName`. The former uses WSMan/WinRM, the latter uses OpenSSH.
- WSMan's `trustedhosts` file is like SSH's `known_hosts` file. It's a list of remote target servers that "this" source machine can connect to.
- Unfortunately, on linux, PowerShell 7 does not include cmdlets for:
  - Managing services (like `Start-Service`, `Set-Service` etc).
  - WMI services (like `Get-WmiObject`, `Get-CimInstance` etc).

## Other Misc Considerations

- [ ] WinExe
- [ ] [WinRS](https://github.com/marcanpilami/winrs)
- [ ] [ImPacket](https://github.com/SecureAuthCorp/impacket)
- [ ] PowerShell DSC
- [ ] Chef / puppet
- [ ] Azure VM script extensions
- [ ] CloudInit
- [ ] Run windows emulator on linux?
- [ ] Can PSExecSvc.exe be extracted and installed as a service remotely?
- [ ] Use WMIC?
- [ ] Can.NET core use ServiceController APIs on linux?
