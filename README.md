Simple Website based on Zend2 (The ZendSkeletonApplication from http://framework.zend.com/)
=======================

Introduction
------------
This is a simple, skeleton application using the ZF2 MVC layer and module
systems. This application is meant to be used as a starting place for those
looking to get their feet wet with ZF2.

Installation
------------

The source are complete.

Installation Steps from following website have been already done
http://framework.zend.com/manual/current/en/ref/installation.html

Just clone the source to your web folder, and config the according virtual host, it will work.

If you don't know how to set a virtual host, following is an example for apache user


Apache Virtual Host Setup
-------------------------

1. add row

NameVirtualHost *:80

into file

/etc/apache2/ports.conf

for example, you can put this row at the end of the file.


2 add file zend2_simple_sample.conf in path

 /etc/apache2/sites-available/


3 file zend2_simple_sample.conf which created in step 2 contains following content:

<VirtualHost *:80>
ServerName zend2_simple_sample
DocumentRoot /var/www/zend2_simple_sample/public

<Directory /var/www/zend2_simple_sample/public>
AllowOverride All
Require all granted
</Directory>
ErrorLog /var/log/apache2/error.log
LogLevel warn
</VirtualHost>

the path /var/www/zend2_simple_sample means that the folder zend2_simple_sample is under /var/www

4. install apache and php

make sure that apache2 and php is installed on your computer.
if apache2 or php is not yet installed, please install them by following command:

sudo apt-get update
sudo apt-get install apache2
sudo apt-get install php5 libapache2-mod-php5 php5-mcrypt

make sure index.php exists in IfMOdule of file /etc/apache2/mods-enabled/dir.conf

<IfModule mod_dir.c>
DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>

5 ensite, allow rewrite

sudo a2ensite zend2_simple_sample.conf
sudo a2enmod rewrite
sudo service apache2 restart

6.
add following line into  /etc/hosts 

127.0.0.1 zend2_simple_sample


7.
the website is running now under http://zend2_simple_sample 

![alt tag](https://raw.github.com/username/projectname/branch/path/to/img.png)