::Install Laravel on Ubuntu 22.04::
___________________________________

step 1: Step 1. Update the System:
----------------------------------
- sudo apt-get update -y && sudo apt-get upgrade -y

step 2: Install Apache Web Server:
----------------------------------
* Install the Apache Web server with the following command..
- sudo apt install apache2

* Once, installed start and enable the service..
- sudo systemctl enable apache2 && sudo systemctl start apache2

* Check if the service is up and running..
- sudo systemctl status apache2

Step 3. Install PHP8.1 with dependencies:
-----------------------------------------

* To install the PHP8.1 along with extensions execute the following command..
- sudo apt-get install php8.1 php8.1-cli php8.1-common php8.1-imap php8.1-redis php8.1-snmp php8.1-xml php8.1-zip php8.1-mbstring php8.1-curl

Step 4. Install Composer:
-------------------------
* We need to install the Composer responsible for installing all the Laravel components.
- curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer
**or
- sudo apt install composer

* Check the Composer installation..
- composer

Step 5. Install Laravel:
------------------------
* Go into the document root of the website and install Laravel with the composer. In this blog post we will use the default apache2 document root..
- cd /var/www/html/
- sudo composer create-project laravel/laravel "YOUR APPLICATION NAME"

* Go into the test-project directory and set the correct permissions..
- cd /var/www/html/test-project
- chown -R www-data:www-data .
- chmod -R 775 storage/

Step 6. Create Apache Virtual Host File:
----------------------------------------
* Go into the Apache directory where the configuration files are stored and create a configuration file for the Laravel application.
- cd /etc/apache2/sites-available/
- sudo touch laravel.conf

* Paste the following lines of code, save the file and close it.
- sudo vi laravel.conf
-------paste this all following lines code...
<VirtualHost *:80>
ServerName "IP Address"
DocumentRoot /var/www/html/test-project/public

<Directory /var/www/html/test-project>
AllowOverride All
</Directory>

ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combined

</VirtualHost>

* Enable the Apache configuration for Laravel.
- sudo a2ensite laravel.conf

* Check the syntax:
- apachectl -t

* If the syntax is OK, restart the Apache service.
- systemctl reload apache2

"Once, the Apache service is restarted you can access the Laravel website at 'IP ADDRESS'..."
_________________________________________________________________________
REF: https://www.rosehosting.com/blog/how-to-install-laravel-on-ubuntu-22-04/


