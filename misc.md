
## Misc

- [ ] WinExe
- [ ] WinRM
- [ ] https://github.com/diyan/pywinrm
- [ ] https://github.com/marcanpilami/winrs
- [ ] WMI
- [ ] [ImPacket script](https://github.com/SecureAuthCorp/impacket)

## Misc Notes

- The `-ComputerName` options is no longer available in some cmdlets (starting PS 7 onwards).
- Difference between `-ComputerName` vs `-HostName`. The former uses WSMan/WinRM, the latter uses OpenSSH.
- WSMan's `trustedhosts` file is like SSH's `known_hosts` file. It's a list of remote target servers that "this" source machine can connect to.

## Misc Considerations

- [ ] PowerShell DSC
- [ ] Chef / puppet
- [ ] Azure VM script extensions
- [ ] CloudInit
- [ ] Run windows emulator on linux?