# Install Windows Subsystem for Linux 2

WSL2 will install Linux on `C:`.  

## Install
Powershell:  
`wsl --install`

## Manual Install
### Enable WSL2
Enable Windows features:
- Virtual Machine Platform
- Windows Subsystem for Linux  

Reboot Windows, and enable WSL2 as the default in Windows Power Shell   
`PS> wsl --set-default-version 2` 

### Download Linux
Install any Linux dostro from the **Microsoft Sore**, accessed from the Start menu. **Ubuntu** is a good choice.  
_Note: someone commented in a forum to avoid Microsoft Store_

## Launch Linux
- Install and use Windows Terminal
- Click Ubuntu icon in the start menu
- From PowerShell `ubuntu`
- From POwerShell `wsl.exe`, then `exit`

## Update Linux
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
sudo apt-get autoremove
```

## Move Linux Disk Image
Move Linux disk image from `C:` to `D:\wsl`. In a Windows Power Shell terminal:
```
mkdir D:\backup
wsl --export Ubuntu D:\backup\ubuntu.tar
wsl --unregister Ubuntu
mkdir D:\wsl
wsl --import Ubuntu D:\wsl\ D:\backup\ubuntu.tar
wsl --list
ubuntu config --default-user <yourname>
```

## Accessing Linux Files from Windows
In File Explorer or any file open dialog
```
\\wsl$\
\\wsl$\Ubuntu
```

## Accessing Windows Files from Linux
Windows drives are mounted in the Linux /mnt/ directory. For example, your personal Users folder at C:\Users\<yourname> is available at:
`/mnt/c/Users/<yourname>`

## Running Linux Commands from Windows
Any Linux (bash) shell command can be run from a Windows Powershell or command line terminal using `wsl`:  
`wsl <linux-command>`  
For example, `wsl ls -la`

## Running Windows Applications
Any Windows executable can be launched from Linux (it’s normally necessary to specify the .exe extension). For example
```
explorer.exe .
notepad.exe ~/.bashrc
code ~/projects/mywebsite
```

## Powershell wsl commands
```
wsl (launch default shell)
wsl --list --running
wsl --list --all
wsl --status
wsl --terminate
wsl --shutdown
```

## Linux GUI Apps
```
gedit
gimp
nautilus
vlc
xcalc
xclock
xeyes
google-chrome
```



## Issues
1. Windows executable not launched from Linux  
_Workaround: restart Windows_  

2. Linux Files accessible from Windows only at startup  
_Workaround: restart Windows_

_Debugging_:  
```
marco@LTMARCOP01:~$ dmesg |grep 9p  

[    0.565732] 9p: Installing v9fs 9p2000 file system support
[    0.567699] FS-Cache: Netfs '9p' registered for caching
[    0.720207] 9pnet: Installing 9P2000 support
[    2.545714] 9pnet_virtio: no channels available for device drvfs
[    2.780407] 9pnet_virtio: no channels available for device drvfs
```



