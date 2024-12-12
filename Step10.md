# 10) All users should have full access (Read, Write and Execute Permissions) to their shared Folder. However, IT and Management should full access to all shared Folders.

fyrts we need to make the folders
```
sudo mkdir sambashare/Tolvudeild
sudo mkdir sambashare/Sala
sudo mkdir sambashare/Stjornun
```

next we need to assign owners to each folder
```
sudo chown :Tolvudeild sambashare/Tolvudeild
sudo chown :Sala sambashare/Sala
sudo chown :Stjornun sambashare/Stjornun
```

now set permissions 
```
sudo chmod 770 sambashare/Tolvudeild
sudo chmod 770 sambashare/Sala
sudo chmod 770 sambashare/Stjornun
```

and now to give Tölvudeild full access
```
sudo setfacl -m g:Tolvudeild:rwx sambashare/Sala
sudo setfacl -m g:Tolvudeild:rwx sambashare/Stjornun
sudo setfacl -m g:Tolvudeild:rwx sambashare/Tolvudeild
```

now checking sambashare it should look like this(if not try *sudo reboot* and check again)
<img tytle="samba" width="600" src="/ImageFolder/samba4.png">
