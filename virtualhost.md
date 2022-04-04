
# VirtualHost Configuration of our Websites

## TIPS & TRICKS

- Live mod php.ini file 
  - deny override --> AllowOverride None
  - deny the use of .htaccess put the code in the virtualhost 
      per website that needs it

- VirtualHost   

- Listen to different ports
  - https://www.youtube.com/watch?v=Vn5PWMKq-wg


---


## Local

### Scorpiocoding.com
```text
  <VirtualHost *:80>

    ServerName scorpiocoding.loc
    ServerAlias www.scorpiocoding.loc
    ServerAlias m.scorpiocoding.loc
    ServerAlias syops.scorpiocoding.loc
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/scorpiocoding/public

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined

    <Directory /var/www/scorpiocoding/public>
            Options Indexes FollowSymlinks
            AllowOverride All
            Require all granted
    </Directory>

  </VirtualHost>
```


# #Live (OVH) 01/04/2022



---
.
## Code Sample .htaccess
### example of a .htaccess file
```text
  <IfModule mod_rewrite.c>
    RewriteEngine on

    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_FILENAME} !-f

    RewriteRule ^ index.php [L]

  </IfModule>
```

### no .htacces file direct in the virtualhost file
```text
  <VirtualHost *:80>

    ServerName scorpiocoding.loc
    ServerAlias www.scorpiocoding.loc
    ServerAlias m.scorpiocoding.loc
    ServerAlias syops.scorpiocoding.loc
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/scorpiocoding/public

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined

    <Directory /var/www/scorpiocoding/public>
            Options FollowSymlinks
            AllowOverride All
            Require all granted
    </Directory>

    <IfModule mod_rewrite.c>
      RewriteEngine on

      RewriteCond %{REQUEST_FILENAME} !-d
      RewriteCond %{REQUEST_FILENAME} !-f

      RewriteRule ^ /index.php [L]
    </IfModule>

</VirtualHost>
```
#### !! note the forward slash in front of /index.php has been added


## Listen to different Ports

### Website 1 : siteOne.conf
- step 1 add the following the the top of the file
  ```text
  Listen 2000
  ```

- step 2 mod the virtual host
  ```text
  <VirtualHost *:2000>
  </VirtualHost>
  ```
### Tips & tricks
- linux command to checkout your network  
  `ss -nat`

- the `ports.conf` file location is:
  `/etc/apache2/ports.conf`