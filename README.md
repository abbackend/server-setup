# SERVER SETUP (Ubuntu 20.*)
## We need to setup the following plugins.
| # | Plugin |
| ------ | ------ |
| 1 | Apache Server |
| 2 | MySQL Server |
| 3 | PHP |
| 4 | PHP MyAdmin |
| 5 | Composer |
| 6 | Git |

## Apache Server
``` sh
# Install
sudo apt-get install apache2
```
``` sh
# Config Test
sudo apache2ctl configtest
```
``` sh
# Check Config
sudo nano /etc/apache2/apache2.conf
```
``` sh
# Restart
sudo systemctl restart apache2
```
``` sh
# Set Permission
sudo chmod 777 -R /var/www/html
```
``` sh
# Unistall
sudo apt-get remove --purge apache2
```

## MySQL Server
``` sh
# Install
sudo apt-get install mysql-server
```
``` sh
# Open Mysql
sudo mysql
```
``` sh
# Set Root Password
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'root';
```
``` sh
# Restart
sudo systemctl restart mysql
```
``` sh
# Unistall
sudo apt-get remove --purge mysql-server
```

## PHP
``` sh
# Install
sudo apt-get install php libapache2-mod-php php-mysql
```
``` sh
# Change PHP Version (5.4 > 7.4)
sudo a2dismod php5.4 && sudo a2enmod php7.4
```
``` sh
# Change CLI Version (5.4 > 7.4)
sudo update-alternatives --set php /usr/bin/php7.4
sudo update-alternatives --set phar /usr/bin/phar7.4
sudo update-alternatives --set phar.phar /usr/bin/phar.phar7.4
```
``` sh
# Unistall
sudo apt-get remove --purge php php*
```

## PHP MyAdmin
```sh
# Install
sudo apt-get install phpmyadmin
```
```sh
# Link To Apache Server
sudo nano /etc/apache2/apache2.conf
> Note: Add this line at bottom of the file 'Include /etc/phpmyadmin/apache.conf'
```
```sh
# Unistall
sudo apt-get remove --purge phpmyadmin
```

## Composer
```sh
# Install
sudo apt-get install composer
```
```sh
# Unistall
sudo apt-get remove --purge composer
```

## GIT
```sh
# Install
sudo apt-get install git
```
```sh
# Unistall
sudo apt-get remove --purge git
```
