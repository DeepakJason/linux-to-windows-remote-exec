# linux-to-windows-remote-exec

Table of contents

- [ ] Powershell Remoting / PSSession
- [ ] Powershell Core
- [ ] PowerShell DSC
- [ ] Chef / puppet
- [ ] Azure VM script extensions
- [ ] CloudInit
- [ ] PSExec
- [ ] WinExe
- [ ] WSMan
- [ ] WinRM
- [ ] WMI
- [ ] [ImPacket script](https://github.com/SecureAuthCorp/impacket)
- [ ] OpenSSH
- [ ] Run windows emulator on linux?

Components

- [ ] Mounting a remote windows share (`admin$`) on linux
  -  https://linuxize.com/post/how-to-mount-cifs-windows-share-on-linux/
- [ ] Controlling services remotely
  - Can PSExecSvc.exe be extracted and installed as a service remotely?
  - Or will we have to author our own service? 

## Powershell Remoting / PSSession




## PSExec

PSExec can only be installed on a Windows machine.

- Target (Windows) prerequisites:
  - The `File and Printer Sharing for Microsoft Networks` feature must be enabled in order for PSExec to work.

- Source (Windows) prerequisites:
  - PSExec must be installed.

- Source (Linux) prerequisites:
  - N/A

Resources
- https://adamtheautomator.com/psexec/
- https://www.contextis.com/en/blog/lateral-movement-a-deep-look-into-psexec
- https://www.mindpointgroup.com/blog/lateral-movement-with-psexec
- 
