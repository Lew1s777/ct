# samba #
```
#smb=server message block
```

installation
---
just use your package manager install the package ```samba```.

configuration file
---

main config file ```/etc/samba/smb.conf```

add the [server] period(optional:change samba user name to what ever you like)

```
$ cat /etc/samba/smb.conf

...
[server]
        comment = smb server running on fedora Linux
        path = /media/data
        public = yes
        writable = yes
        guest ok = yes
```

Create an account
---
- create an account in your linux system
  - e.p.,create an account named server:
  ```
  useradd server
  ```

- create an samba user

  - e.p.:
```
pdbedit -a -u server
```

Restart smb service
---
```
systemctl restart smb.service
#systemctl restart smbd.service           #on some particular distro
```

Check port
---
(package ```net-tools``` required)
```
netstat -tunlp | grep smb
```

Check firewall
---
[dependent on your particular system]

Disable SELinux
---
SELinux will make the remote users have no access to the shared directory. Disable it with the following command(as root)
```
setenforce 0
```

Conect to the samba server
---
- install package ```cifs-utils```
- mount cifs
```
#need to change server id,mount point,server password to your own server
#for some reasons,I made the cache disabled.If you want the service react faster,enable the cache
sudo mount.cifs //192.168.3.2/server /mnt -o username=server,password=12345678,vers=3.0,sec=ntlmssp,iocharset=utf8,uid=0,gid=0,cache=none
```
