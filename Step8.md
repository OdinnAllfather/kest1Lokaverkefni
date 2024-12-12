# 8) All users should have access to their home directory only, except for the IT group they should have full access to all directories.

to give Tölvudeild access to all home directories do the following commands
```
sudo chgrp -R sharedgroup /home
sudo chmod -R g+rx /home
```
