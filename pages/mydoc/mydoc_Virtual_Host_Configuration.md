---
title: Create a Virtual Host Configuration
permalink: mydoc_virtual_host_configuration.html
keywords: virtual host, config
sidebar: mydoc_sidebar
folder: mydoc
---


Follow the below steps to create a virtual Host Configuration:
1. Navigate to the following directory `/etc/apache2/sites-available/owncloud.conf`:
2. nano /etc/apache2/sites-available/owncloud.conf

2. Edit the owncloud.config file and add the following content:
    ```
    Alias /owncloud "/var/www/owncloud/"

    <Directory /var/www/owncloud/>
    Options +FollowSymlinks
    AllowOverride All

    <IfModule mod_dav.c>
    Dav off
    </IfModule>

    SetEnv HOME /var/www/owncloud
    SetEnv HTTP_HOME /var/www/owncloud
    ```
3. Save and Exit.

## Enable the Virtual Host Configuration
To enable the virtual host configuration, run the following commands:
```
a2ensite owncloud.conf
service apache2 reload
```

## Enable the Recommended Apache Modules
To enable the recommended Apache Modules. run the following commands:
```
echo "Enabling Apache Modules"
a2enmod dir env headers mime rewrite setenvif
```

## Restart Apache Web Server and MariaDB Database
To restart Apache and MariaDB, run the following commands:
```
systemctl restart apache2
systemctl restart mariadb
```

ownCloud is now installed. You can confirm that it is ready to use by pointing your web browser to your ownCloud installation.

Example:
```
localhost/ownCloud
```