# Prepare Ubantu 20.04 Server

Before you install the ownCloud, you've to prepare the Ubuntu 20.04 server by installing the required packages:
* Apache webserver
* Database
* PHP 7.4 and related modules



## Install Apache webserver
To install Apache webserver, run the following command:
```
apt install libapache2-mod-php apache2
```

TIP: You can run the following command to verify the status of Apache Webserver installation.
```
systemctl status apache2
```


## Install Database
ownCloud supports the following database products:
* MariaDB (recommended)
* SQ Lite
* PostgreSQL
* Oracle 11g (Enterprise-edition only)

MariaDB is the recommended database for ownCloud. To install MariaDB, run the following commands:
```
apt install mariadb-server
sudo mysql_secure_installation
```
TIP: You can run the following command to verify the status of MariaDB.
```
systemctl status mariadb
```

NOTE: To know more about other database products installation, refer to [Supported DataBases](https://doc.owncloud.com/server/10.7/admin_manual/installation/manual_installation/manual_installation_db.html#possible-databases "Supported DataBases").

## Install PHP 7.4 and related modules
To install PHP 7.4 and other releated modules, run the following commands:
```
apt install php-fpm php-cgi
apt install php
apt install php-mysql php-mbstring php-intl php-redis php-imagick php-igbinary php-gmp php-bcmath php-curl php-gd php-zip php-imap php-ldap php-bz2 php-ssh2 php-phpseclib
apt install php-dev libsmbclient-dev php-pear
```

TIP:  You can run the following command to check the PHP version installed in your server:
```
php -v
```

IMPORTANT: If you've mutilple concurrent PHP versions, you must tell your Web Server and CLI environment which one to use. For more information, refer to [Multiple Concurrent PHP Versions](https://doc.owncloud.com/server/10.7/admin_manual/installation/manual_installation/server_prep_ubuntu_20.04.html#multiple-concurrent-php-versions "Multiple Concurrent PHP Versions").
