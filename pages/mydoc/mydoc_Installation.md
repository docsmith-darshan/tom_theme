# ownCloud Installation
Run the following commands in your terminal to complete the installation.

# Configure the MariaDB Database
To configure the database, follow the below steps:

1. Login into MariaDB, by running the following command:
    ```
    mysql --user=root -p
    ```
2. Create a new database for ownCloud:
    ```
    CREATE DATABASE <name>;
    ```
    For example:
    ```
    CREATE DATABASE ownclouddb;
    ```
3. Create a new database user with password:
    ```
    CREATE USER 'dbadmin'@'localhost' IDENTIFIED BY 'password';
    ```
    Example:
    ```
    CREATE USER 'ownclouduser'@'localhost' IDENTIFIED BY '1234';
    ```
4. Grant all the privileges to user:
    ```
    GRANT ALL PRIVILEGES ON *.* TO 'dbadmin'@'localhost' WITH GRANT OPTION;
    ```
    Example:
    ```
    GRANT ALL PRIVILEGES ON *.* TO 'ownclouduser'@'localhost' WITH GRANT OPTION;
    ```
5. Reload the privilages:
    ```
    FLUSH PRIVILEGES;
    ```
6. Exit the MariaDB database:
    ```
    exit
    ```
# Download ownCloud
To install ownCloud binaries, you have to download the required package.
Before you download the ownCloud package, you must navigate to the directory `/var/www`. 

Follow the below steps to donwload ownCloud:
1. Navigate to the `/var/www` directory:
    ```
    cd /var/www
    ```

2. To download the latest archive of the ownCloud version, go to [ownCloud Download page](https://owncloud.com/download-server/ "ownCloud Download page") and select the package that fits your needs.  You can download either the .tar.bz2 or .zip archive.

3. Copy the link of the selected file and run following command to download it:
    ```
    wget https://download.owncloud.org/community/owncloud-complete-yyyymmdd.tar.bz2
    ```
    Example:
    ```
    wget https://download.owncloud.org/community/owncloud-complete-20210326.tar.bz2
    ```
4. Extract the archive contents and run the unpacking command for your tar archive:
    ```
    tar -xjf owncloud-complete-yyyymmdd.tar.bz2
    ```
    Example:
    ```
    tar -xjf owncloud-complete-20210326.tar.bz2
5. Set the ownership and permissions for ownCloud directory, by running the follwoing commands:
    ```
    chown -R www-data:www-data /var/www/owncloud
    chmod -R 755 /var/www/owncloud
    ```

# Create a Virtual Host Configuration
Follow the below steps to create a virtual Host Configuration:
1. Navigate to the following directory `/etc/apache2/sites-available/owncloud.conf`:
    ```
    nano /etc/apache2/sites-available/owncloud.conf
    ```
2. Add the following config lines:
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

# Enable the Virtual Host Configuration
To enable the virtual host configuration, run the following commands:
```
a2ensite owncloud.conf
service apache2 reload
```

# Enable the Recommended Apache Modules
To enable the Recommended Apache Modules. run the following commands:
```
echo "Enabling Apache Modules"
a2enmod dir env headers mime rewrite setenvif
```

# Restart Apache Web Server and MariaDB Database
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
