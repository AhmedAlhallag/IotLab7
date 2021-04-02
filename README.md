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

### Installing MySQL server and trying to host a single PHP page on Apache
```
sudo apt-get install mysql-server

sudo mysql_secure_installation

sudo mysql -u root –p

sudo apt-get install php libapache2-mod-php

sudo apt-get install php-mysql php-curl php-gd php-json php-zip php-mbstring php-mcrypt

sudo service apache2 restart

sudo nano /var/www/html/index.php
```
- Type in the following code:

```php
<?php
echo "My first php website!";  
?>
```
- Apache should host any php file inside that directory, Try to access that page via  x.x.x.x/index.php

### Installing phpMyAdmin web application
```
sudo apt-get install phpmyadmin

sudo mysql -u root -p

sudo service apache2 reload

sudo service apache2 restart

sudo phpenmod mbstring
```
-  give apache the ability to host phpmyadmin application and make it accessible for us
```
sudo nano /etc/apache2/apache2.conf

Include /etc/phpmyadmin/apache.conf

sudo service apache2 restart
```
### Modifying root's password so we can access the website
```
sudo mysql -u root -p

SELECT user,plugin,host FROM mysql.user WHERE user = 'root';
```
- you can change the password to any value
```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '123';

SELECT user,plugin,host FROM mysql.user WHERE user = 'root';

FLUSH PRIVILEGES;
```
- hit CTRL+Z
