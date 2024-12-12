# 11) ) Install and configure SSH protocol, so IT and Management users have remote access to the server via SSH and test your configuration.

Fyrst install SSH 
```
sudo apt update
sudo apt install openssh-server -y
```

next we need to edit ssh
```
sudo nano /etc/ssh/sshd_config
```

add this to the bottom
```
AllowGroups Tolvudeild Stjornun
```
<img tytle="sshd_config" width="600" src="/ImageFolder/sshd.png">

save and exit the restart the ssh
```
sudo systemctl restart ssh
```

now to test type following commands
```
su - user_tolvudeild
```
provide password set in the userList.csv
```
ssh localhost
```
