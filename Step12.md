# 12) Install apache2 web server with SSL certificate and configure a demo site, the site should be accessible via the URL https://www.yourname.local
<!--I appologise if ths information is incorrect beacause this is the point my vm broke-->

fyrst uppdate
```
sudo apt update
sudo apt upgrade -y
```

next install apche2
```
sudo apt install apache2 -y
```

now we need to generate an SSL Certificate
For a local site, you can create a self-signed SSL certificate:
```
sudo mkdir /etc/ssl/certs/mydomain
sudo openssl req -x509 -newkey rsa:4096 -keyout /etc/ssl/certs/mydomain.key -out /etc/ssl/certs/mydomain.crt -days 365 -nodes
```
This will generate a private key (mydomain.key) and a certificate (mydomain.crt). Fill in the requested information during the prompt. For Common Name (CN), use hostname.local.


next we need to configur the demo site
edit this file
```
sudo nano /etc/apache2/sites-available/yourname.local.conf
```

in the new file add this 
```
<VirtualHost *:80>
    ServerAdmin webmaster@yourname.local
    ServerName yourname.local
    Redirect permanent / https://yourname.local/
</VirtualHost>

<VirtualHost *:443>
    ServerAdmin webmaster@yourname.local
    ServerName yourname.local
    DocumentRoot /var/www/yourname.local

    SSLEngine on
    SSLCertificateFile /etc/ssl/certs/mydomain.crt
    SSLCertificateKeyFile /etc/ssl/certs/mydomain.key

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
<img tytle="local conf" width="600" src="ImageFile/localConf.png">

now lets create a document root
type out following command
```
sudo mkdir -p /var/www/yourname.local
echo '<html><body><h1>Welcome to your demo site!</h1></body></html>' | sudo tee /var/www/yourname.local/index.html
```

now we restart
```
sudo a2ensite yourname.local.conf
sudo systemctl reload apache2
```

next edit hosts 
```
sudo nano /etc/hosts
```

and add this line
```
127.0.0.1    yourname.local
```

then type this and after that the websit should be accessible via "https://yourname.local"
```
sudo ufw allow 80,443/tcp
```

it should look like this
<img tytle="demo site" width="700" src="ImageFile/demoSite.png">
