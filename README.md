# Table of contents

- [x] PSExec
- [x] Powershell remoting over WSMan/WinRM
- [ ] PowerShell remoting over OpenSSH
- [ ] WinExe
- [ ] WinRM
- [ ] https://github.com/diyan/pywinrm
- [ ] WMI
- [ ] [ImPacket script](https://github.com/SecureAuthCorp/impacket)
- [ ] OpenSSH

Components

- [ ] Controlling services remotely
  - Can PSExecSvc.exe be extracted and installed as a service remotely?
  - Or will we have to author our own service?
  - Use powershell?
  - Use WMI?
  - Use .NET core?

## PSExec

| Supported Configurations | Notes                                |
| ------------------------ | ------------------------------------ |
| ❌ Linux -> Windows       | PSExec cannot be installed on Linux. |
| ✅ Windows -> Windows     | N/A                                  |

| Machine          | Prerequisites                                                                                                                                                 |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Target (Windows) | - The `File and Printer Sharing for Microsoft Networks` feature must be enabled in order for PSExec to remotely establish a connection to the target machine. |
| Source (Windows) | - PSExec must be installed.                                                                                                                                   |
| Source (Linux)   | - Not supported.                                                                                                                                              |

## Powershell remoting over WSMan/WinRM

| Supported Configurations | Notes                                    |
| ------------------------ | ---------------------------------------- |
| ❌ Linux -> Windows       | WSMan / WinRM is not supported on Linux. |
| ✅ Windows -> Windows     | N/A                                      |

| Machine          | Prerequisites                                                                                                                                                                                                                               |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Target (Windows) | - Enable PowerShell remoting by running the `Enable-PSRemoting` cmdlet.<br>- Configure the WinRM service by running the `winrm quickconfig` command or `Set-WSManQuickConfig` cmdlet.                                                       |
| Source (Windows) | - The remote target machine's IP/hostname must be added to the source machine's WSMan trusted hosts. Use the following cmdlet for this purpose: `Set-Item -path "WSMan:\localhost\Client\TrustedHosts" -value IP-OF-REMOTE-TARGET-MACHINE`. |
| Source (Linux)   | Not supported.                                                                                                                                                                                                                              |

- Notes:
  - The `Enter-PSSession` or `Invoke-Command` cmdlets can be used to execute commands on a remote machine.

## Powershell remoting over OpenSSH

## Resources

- PSExec internals
  - https://adamtheautomator.com/psexec/
  - https://www.contextis.com/en/blog/lateral-movement-a-deep-look-into-psexec
  - https://www.mindpointgroup.com/blog/lateral-movement-with-psexec
- Mounting a remote windows share (`admin$`) on linux
  - https://linuxize.com/post/how-to-mount-cifs-windows-share-on-linux/
- PowerShell Remoting setup
  - https://blog.quickbreach.io/blog/powershell-remoting-from-linux-to-windows/
  - https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote?view=powershell-7.2
  - https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-7.2
  - https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_requirements?view=powershell-7.2
  - https://docs.microsoft.com/en-us/powershell/scripting/learn/ps101/08-powershell-remoting?view=powershell-7.2
  - https://docs.microsoft.com/en-us/powershell/scripting/learn/remoting/powershell-remoting-faq?view=powershell-7.2
  - https://docs.microsoft.com/en-us/powershell/scripting/learn/remoting/running-remote-commands?view=powershell-7.2
  - https://automateinfra.com/2021/04/12/how-to-connect-windows-to-linux-and-linux-to-windows-using-ssh-powershell-remoting/
  - https://www.netspi.com/blog/technical/network-penetration-testing/powershell-remoting-cheatsheet/
  - https://blog.quickbreach.io/blog/powershell-remoting-from-linux-to-windows/
  - https://4sysops.com/archives/powershell-remoting-between-windows-and-linux/

## Misc Considerations

- [ ] PowerShell DSC
- [ ] Chef / puppet
- [ ] Azure VM script extensions
- [ ] CloudInit
- [ ] Run windows emulator on linux?