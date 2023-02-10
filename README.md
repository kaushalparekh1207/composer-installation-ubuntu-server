# Composer Installation on Ubuntu Server

-> Open Terminal as Root User

Step 1 :
````javascript
sudo apt update
````

Step 2 :
````javascript
sudo apt install php-cli unzip
````
> Follow Above Step if php unzip is not Installed on Your Server

Step 3 :
````javascript
cd ~
curl -sS https://getcomposer.org/installer -o /tmp/composer-setup.php
````

Step 4 :
````javascript
HASH=`curl -sS https://composer.github.io/installer.sig`
````

Step 5 :
````javascript
echo $HASH
````
> Output 
````javascript
e0012edf3e80b6978849f5eff0d4b4e4c79ff1609dd1e613307e16318854d24ae64f26d17af3ef0bf7cfb710ca74755a
````

Step 6 :
````javascript
php -r "if (hash_file('SHA384', '/tmp/composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
````

> Installer Verified

Step 7 :
````javascript
sudo php /tmp/composer-setup.php --install-dir=/usr/local/bin --filename=composer
````

You’ll see output similar to this:
````javascript
Output
All settings correct for using Composer
Downloading...

Composer (version 2.2.9) successfully installed to: /usr/local/bin/composer
Use it: php /usr/local/bin/composer
````

> To test your installation or check Composer Version, run:
````javascript
composer
````
