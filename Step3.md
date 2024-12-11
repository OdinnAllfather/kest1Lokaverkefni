# 3) Configure the hostname of server1 as server1 and domain “YourName.local”, so the FQDN of the server will be server1.yourname.local

fyrst go to your server and open the terminal. Edit the /hostname file
```bash
sudo nano /etc/hostname
```
replace the curent name with *yourname.local*(replace yourname with desired name). It should now look something like this

[hostname](hostname.png)

Next edit the /hosts file.
```bash
sudo nano /etc/hosts
```
replace the top 2 lines with
```
ip 
