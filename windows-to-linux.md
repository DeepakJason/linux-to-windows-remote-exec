# Windows to Linux

## ❌ PSExec

PSExec cannot be installed on Linux

## ✅ OpenSSH

Target machine prerequisites:

- None.

Source machine prerequisites:

- None. OpenSSH is already built-in. Just connect to the target machine with the private SSH key as follows: `ssh username@targetIP -i <path-to-key>`.

## ❌ WinRM

WinRM server cannot be enabled on Linux

## ✅ PowerShell remoting over OpenSSH

Target machine prerequisites:

- PowerShell 7 is required on the target machine. Install PowerShell 7 using the ([steps here](https://docs.microsoft.com/en-us/powershell/scripting/install/install-ubuntu?view=powershell-7.2#installation-via-package-repository)).
- Configure the `sshd_config` file and restart the server using [steps 3-4 outlined here](https://docs.microsoft.com/en-us/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core?view=powershell-7.2#install-the-ssh-service-on-an-ubuntu-linux-computer).

Source machine prerequisites:

- PowerShell 7 is required on the source machine, while the built-in version on most windows machines is PowerShell 5. Install PowerShell 7 using the ([steps here](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.2)).
- Once the target machine has been configured, you can connect to it via a PSSession as follows: `Enter-PSSession -HostName IP-OF-REMOTE-TARGET-MACHINE -UserName ADMIN-USERNAME-OF-REMOTE-TARGET-MACHINE -KeyFilePath PATH-TO-SSH-PRIVATE-KEY`.

## ❌ Powershell remoting over WSMan/WinRM

WinRM server cannot be enabled on Linux
