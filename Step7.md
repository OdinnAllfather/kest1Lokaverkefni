# Create a bash script that will import all user accounts into their groups respectively.

a. Each user should have his own directory under /home

b. Each user should use bash shell

c. All the user passwords should be encrypted using SSL.

make a bash file called addUser.sh
```
sudo nano addUser.sh
```

write this in the file(replace odiin with your name found with the whoami command)
<image tytle="addUser.csv" width="700" src="ImageFolder/addUser.png">

save and exit then type this command
```
sudo chmod +x addUser.sh
```

then execute addUser with this command
```
./addUser.sh
```
