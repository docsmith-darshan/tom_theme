---
title: Manage Trusted Domains
permalink: mydoc_manage_trusted_domains.html
keywords: virtual host, config
sidebar: mydoc_sidebar
folder: mydoc
---


All URLs which access your ownCloud server must be listed in your `config.php` file, under the trusted_domains setting. Users can access and log into ownCloud only when their URL is listed in the trusted_domains setting.

**Procedure**

1. Edit the `config.php` file:
    ```
    nano /var/www/owncloud/config/config.php
    ```
2. Under trusted domains, enter users URL.
    ```
    'trusted_domains' => [
    0 => 'localhost',
    1 => 'server1.example.com',
    2 => '192.168.1.50',
    ],
    ```
    For example:
    {% include image.html file="trusted_domains.png" alt="Jekyll"  %}
3. Save and Exit.