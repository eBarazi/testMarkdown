# Samba

Install Samba:
```
apt install samba
```

Create user:
```
useradd -m ubunny
```

Add user password:
```
passwd ubunny
```

Add samba password:
```
smbpasswd -a ubunny
```

Edit Samba share config:
```
nano /etc/samba/smb.conf
```
Add the share and user infos:

```
[database]
    path = /home/database
    writable = yes
    guest ok = no
    valid users = ubunny
    force create mode = 770
    force directory mode = 770
    inherit permissions = yes
```

Restart Samba  service:
```
systemctl restart smbd.service
```


Fix Samba share:
```
chown -R ubunuy /home/database
```

Delete lost and found folder:
```
sudo rm -rf /home/database/lost+found
```

to give access to everyone and evry group:
```
chown -R ubunnuy /home/database
```
