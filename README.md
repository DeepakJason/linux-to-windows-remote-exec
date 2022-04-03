# Table of contents

- [Linux to Windows](./linux-to-windows.md)
- [Windows to Linux](./windows-to-linux.md)
- [Resources](./resouces.md)
- [Miscellaneous](./misc.md)


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
