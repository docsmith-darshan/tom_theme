---
title: Server Preparation
permalink: mydoc_server_preparation.html
keywords: Prepare Server
sidebar: mydoc_sidebar
folder: mydoc
---


## Before you Begin

Ensure that you update and upgrade your operating system software. These upgrades can provide security and software fixes that might prevent future problems. To update all packages on your system, run the following command:
```
apt update && apt upgrade -y
```

## Prepare Ubantu 20.04 Server

Before you install the ownCloud, you've to install the following packages on Ubuntu 20.04 server:
* Apache webserver
* Database
* PHP 7.4 and related modules



## Install Apache Webserver
To install Apache Webserver, run the following command:
```
apt install libapache2-mod-php apache2
```

{{site.data.alerts.tip}}
<p>You can also run the following command to verify the status of Apache Webserver installation.</p>
<pre>
systemctl status apache2
</pre>
{{site.data.alerts.end}}


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

{{site.data.alerts.tip}}
<p>You can also run the following command to verify the status of MariaDB.</p>
<pre>
systemctl status mariadb
</pre>
{{site.data.alerts.end}}



{% include note.html content="To know more about other database products installation, refer to [Supported DataBases](https://doc.owncloud.com/server/10.7/admin_manual/installation/manual_installation/manual_installation_db.html#possible-databases). " %}


## Install PHP 7.4 and Related Modules
To install PHP 7.4 and other releated modules, run the following commands:
```
apt install php-fpm php-cgi
apt install php
apt install php-mysql php-mbstring php-intl php-redis php-imagick php-igbinary php-gmp php-bcmath php-curl php-gd php-zip php-imap php-ldap php-bz2 php-ssh2 php-phpseclib
apt install php-dev libsmbclient-dev php-pear
```


{% include important.html content="If you've mutilple concurrent PHP versions, you must tell your Web Server and CLI environment which one to use. For more information, refer to [Multiple Concurrent PHP Versions](https://doc.owncloud.com/server/10.7/admin_manual/installation/manual_installation/server_prep_ubuntu_20.04.html#multiple-concurrent-php-versions). " %}


Next [Configure MariaDB](mydoc_configure_database.html)