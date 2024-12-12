# 5) Install and Configure DNS on server1 for the internal network so hostnames are resolved to IP addresses.
Let's start by updating 

```bash
sudo apt update
sudo apt upgrade -y
```

Next download dns
```bash
sudo apt install bind9 bind9utils bind9-doc -y
```

now edit the configuration files 
```bash
sudo nano /etc/bind/named.conf.local
```

add the following code(replacing hostname with the hostname from step 3)
```linux
zone "hostname.local" {
    type master;
    file "/etc/bind/db.hostname.local";
};
```
<image tytle="named.conf.local" width="600" src="ImageFolder/namedConf.png">

create a new zone file by copying the default zone file, Then edit it
```linux
sudo cp /etc/bind/db.local /etc/bind/db.example.local
sudo nano /etc/bind/db.example.local
```

make it look like this replacing hostname
<image tytle="db.hostname" width="600" src="ImageFolder/dbHostname.png">
<image tytle="db.odinnorn" width="600" src="ImageFolder/dbOdinnorn.png">

next edit the name.conf.options file
```
sudo nano /etc/bind/named.conf.options
```

make it looke like this
```
options {
    directory "/var/cache/bind";

    listen-on { 127.0.0.1; 192.168.1.1; };
    allow-query { localhost; 192.168.1.0/24; };

    recursion yes;
    dnssec-validation auto;

    auth-nxdomain no;    # conform to RFC1035
    listen-on-v6 { any; };
};
```

now restart the dns, then check it status it should say running
<image tytle="dns9" width="600" src="ImageFolder/dns9.png">

finally lets configur the dns
edit this file
```
sudo nano /etc/resolv.conf
```

and add this above nameserver 127.0.1.1
```
nameserver 192.168.1.1
```
