# 9) Install and configure Samba then create network shared folder for each department.

Fyrst install samba
```
sudo apt update
sudo apt install samba
```

now we need to make a directory for sharing
```
mkdir sambashare
```

now we edit this file 
```
sudo nano /etc/samba/smb.conf
```

at the bottom of the file add this 
```
[sambashare]
    comment = Samba on Ubuntu
    path = /home/username/sambashare
    read only = no
    browsable = yes
```
<img tytle="smb.conf" width="600" src="/ImageFolder/smbconf.png">

then save and exit, now we need to restart samba and add a firewall
```
sudo service smbd restart
sudo ufw allow samba
```

now we need a password for samba(username needs to be a system account)
```
sudo smbpasswd -a username
```

and to connect open files and click on connect to server
<img tytle="samba" width="600" src="/ImageFolder/samba1.png">
<img tytle="samba" width="600" src="/ImageFolder/samba2.png">
<img tytle="samba" width="600" src="/ImageFolder/samba3.png">
