WSL2 will install LInux on `C:`.  
  
## Enable WSL2
Enable Windows features:
- Virtual Machine Platform
- Windows Subsystem for Linux  

Reboot Windows, and enable WSL2 as the default in Windows Power Shell   
`PS> wsl --set-default-version 2` 

## Download Linux
Install any Linux dostro from the **Microsoft Sore**, accessed from the Start menu. **Ubuntu** is a good choice.

## Launch Linux
Click Ubuntu icon in the start menu

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