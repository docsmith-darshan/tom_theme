---
title: Install ownCloud
permalink: mydoc_download_owncloud.html
keywords: download, owncloud, install
sidebar: mydoc_sidebar
folder: mydoc
---


To install ownCloud binaries, you've to download the archive of the latest ownCloud version. You can download either the .tar.bz2 or .zip archive that fits your needs. To install ownCloud, complete the following steps:
 

**Procedure**

1. Navigate to the `/var/www` directory:
    ```
    cd /var/www
    ```

2.  Go to [ownCloud Download page](https://owncloud.com/download-server/ "ownCloud Download page") to select the archive file. 

3. You can select either the .tar.bz2 or .zip archive. To copy the link of the selected archive file, right-click the **Download** button, and then select **copy link address**.

    {% include image.html file="download-owncloud.png" alt="ownCloud Download page" %}

3. Download the selected archive file:

    ```
    wget https://download.owncloud.org/community/owncloud-complete-yyyymmdd.archive_type
    ```
    For Example:
    ```
    wget https://download.owncloud.org/community/owncloud-complete-20210326.tar.

    ```


4. Extract the archive contents:
    ```
    tar -xjf owncloud-complete-yyyymmdd.tar.bz2
    ```
    For Example:
    ```
    tar -xjf owncloud-complete-20210326.tar.bz2
    ```
5. Set the ownership and permissions for ownCloud directory:
    ```
    chown -R www-data:www-data /var/www/owncloud
    chmod -R 755 /var/www/owncloud
    ```

Next [Create a Virtual Host Configuration](mydoc_virtual_host_configuration.html)