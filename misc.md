- Controlling Windows services remotely from a linux machine
  - ❌ PowerShell: Unfortunately, on linux, PowerShell 7 does not include cmdlets for:
    - Managing services (like `Start-Service`, `Set-Service` etc).
    - WMI services (like `Get-WmiObject`, `Get-CimInstance` etc).
  - Can PSExecSvc.exe be extracted and installed as a service remotely?
  - Use WMI?
  - Use .NET core?

    - Also, the `-ComputerName` options is no longer available in this cmdlets (starting PS 7 onwards).



- [ ] WinExe
- [ ] WinRM
- [ ] https://github.com/diyan/pywinrm
- [ ] https://github.com/marcanpilami/winrs
- [ ] WMI
- [ ] [ImPacket script](https://github.com/SecureAuthCorp/impacket)


## Misc Considerations

- [ ] PowerShell DSC
- [ ] Chef / puppet
- [ ] Azure VM script extensions
- [ ] CloudInit
- [ ] Run windows emulator on linux?