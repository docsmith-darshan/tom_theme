---
title: Configure MariaDB
permalink: mydoc_configure_database.html
keywords: configure, database
sidebar: mydoc_sidebar
folder: mydoc
---

It describes the basic configuration steps required to create an administrative user for the MariaDB. To configure MariaDB, complete the following steps: 

**Procedure**

1. Login into MariaDB as a root user:
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
    For Example:
    ```
    CREATE USER 'ownclouduser'@'localhost' IDENTIFIED BY '1234';
    ```
    
4. Grant all the privileges to a user:
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
6. Exit MariaDB:
    ```
    exit
    ```