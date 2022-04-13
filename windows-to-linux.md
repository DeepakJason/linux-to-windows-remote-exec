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

## ❔ PowerShell remoting over OpenSSH

Target machine prerequisites:

- @TODO

Source machine prerequisites:

- Once the target machine has been configured, you can connect to it via a PSSession as follows: `Enter-PSSession -HostName IP-OF-REMOTE-TARGET-MACHINE -UserName ADMIN-USERNAME-OF-REMOTE-TARGET-MACHINE`.

## ❌ Powershell remoting over WSMan/WinRM

WinRM server cannot be enabled on Linux
