# Windows to Windows

## ✅ PSExec

Source machine prerequisites:

- PSExec must be installed.

Target machine prerequisites:

- The `File and Printer Sharing for Microsoft Networks` feature must be enabled in order for PSExec to remotely establish a connection to the target machine.


## ✅ Powershell remoting over WSMan/WinRM

Source machine prerequisites:

- The remote target machine's IP/hostname must be added to the source machine's WSMan trusted hosts. Use the following cmdlet for this purpose: `Set-Item -path "WSMan:\localhost\Client\TrustedHosts" -value IP-OF-REMOTE-TARGET-MACHINE`.

Target machine prerequisites:

- Enable PowerShell remoting by running the `Enable-PSRemoting` cmdlet.
- Configure the WinRM service by running the `winrm quickconfig` command or `Set-WSManQuickConfig` cmdlet.

Notes:

- The `Enter-PSSession` or `Invoke-Command` cmdlets can be used to execute commands on a remote machine.

## Powershell remoting over OpenSSH

Source machine prerequisites:

Target machine prerequisites:

