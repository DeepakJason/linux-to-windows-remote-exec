# Windows to Windows

## ✅ PSExec

Target machine prerequisites:

- The `File and Printer Sharing for Microsoft Networks` feature must be enabled in order for PSExec to remotely establish a connection to the target machine.

Source machine prerequisites:

- PSExec must be installed.

## ✅ OpenSSH

Target machine prerequisites:

- Install the OpenSSH server by following the [steps outlined in this document](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse#install-openssh-using-powershell).

Source machine prerequisites:

- None. Just connect to the target machine using SSH as follows: `ssh username@targetIP`. You'll get prompted for password.

## ✅ Powershell remoting over WSMan/WinRM

Target machine prerequisites:

- Enable PowerShell remoting by running the `Enable-PSRemoting` cmdlet.
- Configure the WinRM service by running the `winrm quickconfig` command or `Set-WSManQuickConfig` cmdlet.

Source machine prerequisites:

- The remote target machine's IP/hostname must be added to the source machine's WSMan trusted hosts. Use the following cmdlet for this purpose: `Set-Item -path "WSMan:\localhost\Client\TrustedHosts" -value IP-OF-REMOTE-TARGET-MACHINE`.
- Once PS remoting is enabled on the target machine, the source machine can use the `Enter-PSSession` or `Invoke-Command` cmdlets to execute commands on the remote target machine.

## ✅ Powershell remoting over OpenSSH

Target machine prerequisites:

- PowerShell 7 is required on the target machine, while the built-in version on most windows machines is PowerShell 5. Install PowerShell 7 using the ([steps here](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.2)).
- Install the OpenSSH server by following the [steps outlined in this document](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse#install-openssh-using-powershell).
- Configure the `sshd_config` file and start the OpenSSH server using [steps 3-5 outlined here](https://docs.microsoft.com/en-us/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core?view=powershell-7.2#install-the-ssh-service-on-a-windows-computer).

Source machine prerequisites:

- Once the target machine has been configured, you can connect to it via a PSSession as follows: `Enter-PSSession -HostName IP-OF-REMOTE-TARGET-MACHINE -UserName ADMIN-USERNAME-OF-REMOTE-TARGET-MACHINE`.
