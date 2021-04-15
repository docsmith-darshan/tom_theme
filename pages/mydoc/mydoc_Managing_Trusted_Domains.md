# Manage Trusted Domains

All URLs used to access your ownCloud server must be white-listed in your config.php file, under the trusted_domains setting. Users are allowed to log into ownCloud only when they point their browsers to a URL that is listed in the trusted_domains setting.

Follow the below steps to add users to trusted domains.
1. Navigate to the follwoing directory `/var/www/owncloud/config/config.php`:
    ```
    nano /var/www/owncloud/config/config.php
    ```
2. A typical configuration may look like this:
    ```
    'trusted_domains' => [
    0 => 'localhost',
    1 => 'server1.example.com',
    2 => '192.168.1.50',
    ],
    ```
3. Save and Exit.