# Sync SSH configuration between Windows and WSL

[Ref](https://superuser.com/a/1700535/1796680)

In order to automatically mount SSH Windows configuration folder in WSL we just need to add the following configuration line to `/etc/fstab` file.
Then just restart WSL and any future changes will synchronize between both systems. 

```
C:\Users\<your Windows username>\.ssh\ /home/<your Linux username>/.ssh drvfs rw,noatime,uid=1000,gid=1000,case=off,umask=0077,fmask=0177 0 0
```