---
title: Configure the MariaDB Database
permalink: mydoc_configure_database.html
keywords: configure, database
sidebar: mydoc_sidebar
folder: mydoc
---

{% include important.html content=" You need to again enter the Database user, Database password, and Database name in the [Installation Wizard](mydoc_installation_wizard.html). " %}

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
    {% include important.html content=" You need to enter the same Database name in the [Installation Wizard](mydoc_installation_wizard.html). " %}

3. Create a new database user with password:
    ```
    CREATE USER 'dbadmin'@'localhost' IDENTIFIED BY 'password';
    ```
    Example:
    ```
    CREATE USER 'ownclouduser'@'localhost' IDENTIFIED BY '1234';
    ```
    {% include important.html content=" You need to enter the same Database user name and password in the [Installation Wizard](mydoc_installation_wizard.html). " %}
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