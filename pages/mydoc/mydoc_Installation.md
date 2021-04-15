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