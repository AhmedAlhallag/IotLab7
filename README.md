# Iot Lab 7: MySQL, PHPMyAdmin, Apache w/ Node-RED on Ubuntu 20.4 AWS

# Installation Instructions:

### Installing Apache server
```
sudo lsof -i -P -n | grep LISTEN

sudo apt-get update

sudo apt-get install apache2

sudo lsof -i -P -n | grep LISTEN

sudo service apache2 status
```
- Type your instance's IP Address in your browser: x.x.x.x

# Installing MySQL server and trying to host a single PHP page on Apache

sudo apt-get install mysql-server

sudo mysql_secure_installation

sudo mysql -u root –p

sudo apt-get install php libapache2-mod-php

sudo apt-get install php-mysql php-curl php-gd php-json php-zip php-mbstring php-mcrypt

sudo service apache2 restart

sudo nano /var/www/html/index.php

Type in the following code:

<?php
echo "My first php website!";  
?>
