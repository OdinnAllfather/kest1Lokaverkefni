# kest1Lokaverkefni
kest1Lokaverkefni Óðinn Örn

## 1) Configure private interface of the server with a static IP address, use 192.168.1.1/24
[Step 1](Step1.md)

<br>

## 2) Configure the hostname of server1 as server1 and domain “YourName.local”, so the FQDN of the server will be server1.yourname.local
[Step 2](Step2.md)

<br>

## 3) Configure client1 hostname as client1 and FQDN as client1.yourname.local
[Step 3](Step3.md)

<br>

## 4) Install and configure DHCP protocol ( isc-dhcp-server) on server1, and make sure the Client1 gets an automatic IP Address, Default Gateway, Domain Name, and DNS automatically from DHCP on server1. 
[Step 4](Step4.md)

<br>

## 5) Install and Configure DNS on server1 for the internal network so hostnames are resolved to IP addresses.
[Step 5](Step5.md)

<br>

## 6) Create (comma separated values) CSV file using the table above.
[Step 6](Step6.md)

<br>

## 7) Create a bash script that will import all user accounts into their groups respectively.
[Step 7](Step7.md)

<br>

## 8) All users should have access to their home directory only, except for the IT group they should have full access to all directories.
[Step 8](Step8.md)

<br>

## 9) Install and configure Samba then create network shared folder for each department.
[Step 9](Step9.md)

<br>

## 10) All users should have full access (Read, Write and Execute Permissions) to their shared Folder. However, IT and Management should full access to all shared Folders.
[Step 10](Step10.md)

<br>

## 11) Install and configure SSH protocol, so IT and Management users have remote access to the server via SSH and test your configuration.
[Step 11](Step11.md)

<br>

## 12) Install apache2 web server with SSL certificate and configure a demo site, the site should be accessible via the URL https://www.yourname.local
[Step 12](Step12.md)
