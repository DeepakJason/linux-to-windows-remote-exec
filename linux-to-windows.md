# Linux to Windows

## ❌ PSExec

PSExec cannot be installed on Linux

## ✅ OpenSSH

Same steps [as outlined in this document](./windows-to-windows.md#✅-openssh)

## ✅ WinRM

Target machine prerequisites:

- None.

Source machine prerequisites:

- Ensure python3 is installed.
- Install pip as follows: `sudo apt install python3-pip`.
- Install [pywinrm](https://github.com/diyan/pywinrm) as follows: `pip install pywinrm`.
- Install additional dependencies for kerberos authentication:
  - On Debian/Ubuntu:
    - `sudo apt-get install gcc python-dev libkrb5-dev`
    - `pip install pywinrm[kerberos]`
  - On RHEL/CentOS/etc:
    - `sudo yum install gcc python-devel krb5-devel krb5-workstation python-devel`
    - `pip install pywinrm[kerberos]`
- Start python3 and run the below snippet
  
  ```python
  import winrm
  s = winrm.Session('IP-OF-REMOTE-TARGET-MACHINE', auth=('ADMIN-USERNAME-OF-REMOTE-TARGET-MACHINE', 'ADMIN-PASSWORD-OF-REMOTE-TARGET-MACHINE'), transport='ntlm')
  r = s.run_cmd('ipconfig', ['/all'])
  r.status_code
  r.std_out
  ```

Notes:

- [Details on copying files from linux to windows over SMB](./misc.md#how-to-copy-files-from-linux-to-windows-over-smb)

## ✅ Powershell remoting over OpenSSH

Same steps [as outlined in this document](./windows-to-windows.md#✅-powershell-remoting-over-openssh)
