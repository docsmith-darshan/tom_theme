---
title: Download ownCloud
permalink: mydoc_download_owncloud.html
keywords: download, owncloud, install
sidebar: mydoc_sidebar
folder: mydoc
---


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
5. Set the ownership and permissions for ownCloud directory, by running the following commands:
    ```
    chown -R www-data:www-data /var/www/owncloud
    chmod -R 755 /var/www/owncloud
    ```