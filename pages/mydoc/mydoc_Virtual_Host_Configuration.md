---
title: Create a Virtual Host Configuration
permalink: mydoc_virtual_host_configuration.html
keywords: virtual host, config
sidebar: mydoc_sidebar
folder: mydoc
---
On Ubuntu systems, Virtual Host Configuration files are located in `/etc/apache2/sites-available` directory. You have to create an `owncloud.conf` file in the same directory.


**Procedure**
1. Create an `owncloud.conf` file in the following directory:

    ```
    nano /etc/apache2/conf-available/owncloud.conf
    ```

2. Add the following content in the `owncloud.config` file:
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

**Enable the Virtual Host Configuration**

To enable the virtual host configuration, run the following commands:
```
a2ensite owncloud.conf
service apache2 reload
```

**Enable the Recommended Apache Modules**

To enable the recommended Apache modules, run the following commands:
```
echo "Enabling Apache Modules"
a2enmod dir env headers mime rewrite setenvif
```

**Restart Apache Web Server and MariaDB**

To restart Apache and MariaDB, run the following commands:
```
systemctl restart apache2
systemctl restart mariadb
```

ownCloud is successfully installed. Now use your web browser to access the ownCloud and view the ownCloud setup page. Your ownCloud is accessible from `http://< your-owncloud-domain >`. To complete the installation wizard, see [Installation Wizard](mydoc_installation_wizard.html).


For Example:
```
http://localhost/ownCloud
```