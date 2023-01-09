		:::WORDPRESS INSTALLATION:::
		----------------------------
* Open Terminal 'Ctrl + Alt + T'
- sudo apt update -y && sudo apt upgrade -y (Update and upgrade the ubuntu)

----------------------------
(step1) Apache2 Install...✅️
----------------------------
- sudo apt install apache2  (Install Apache)
- systemctl status apache2 (view the Apache active status)

* chack apache2 using the IP addres in any browser...

- sudo ufw app list (ufw is a firewall related command)
- sudo ufw allow in "Apache" (in firewall alow the apache2 package)
- sudo ufw status (view the status of firewall)

--------------------------
(step2) MySQL Install...✅️
--------------------------
* Holding the wordpress files need to install MariaDB is an open source fork off MySQL.
-sudo apt install mariadb-server mariadb-client

* Let’s now secure our MariaDB database engine and disallow remote root login.
- sudo mysql_secure_installation

------------------------
(step3) PHP Install...✅️
------------------------
- sudo apt install php php-mysql (Install php)
- vim /var/www/html/info.php (make a file 'info.php')
* Enter the file pest the code 
- <?php
phpinfo();
?>

* Now chack in browser 'https://ip addres/into.php

--------------------------------------
(step4) Create WordPress Database...✅️
--------------------------------------
* Now it’s time to log in to our MariaDB database as root and create a database for accommodating our WordPress data...
- mysql -u root -p

* Create a database for our WordPress installation...
- CREATE DATABASE wordpress_db;
- CREATE USER 'wp_user'@'localhost' IDENTIFIED BY 'password';

* Grant privileges to the user Next, grant the user permissions to access the database...
- GRANT ALL ON wordpress_db.* TO 'wp_user'@'localhost' IDENTIFIED BY 'password';
- FLUSH PRIVILEGES;
- Exit;

----------------------------------
(step5) Install WordPress CMS...✅️
----------------------------------
* Go to your temp directory and download the latest WordPress File...
- cd /tmp && wget https://wordpress.org/latest.tar.gz
* Next, Uncompress the tarball which will generate a folder called “wordpress”...
- tar -xvf latest.tar.gz
* Copy the wordpress folder to /var/www/html/ path...
- sudo cp -R wordpress /var/www/html/
* Run the command below to change ownership of ‘wordpress’ directory...
- sudo chown -R www-data:www-data /var/www/html/wordpress/
* change File permissions of the WordPress folder...
- sudo chmod -R 755 /var/www/html/wordpress/
* Create ‘uploads’ directory...
- sudo mkdir /var/www/html/wordpress/wp-content/uploads
* Finally, change permissions of ‘uploads’ directory...
- sudo chown -R www-data:www-data /var/www/html/w ordpress/wp-content/uploads/
* Open your browser and go to the server’s URL. In my case it’s 'https://server-ip/wordpress'
Done✅️

		End the process of Installation...
		----------------------------------
			
After installation how to full setup wordpress...
::Database setup..
* Goto Terminal 
- sudo mysql -u root -p
enter root password.
* now create a database with command
- create database wordpress;
- show databases;
* add username add password
- create user "tuhinjoy"@"%" identified by "password";
* Acces to the wordpress by this command.
- grant all privileges on wordpress.* to "tuhinjoy"@"%";
Done✅️

ALL DONE GOTO WORDPRESS BY YOUR IP AND FILLUP ALL THE DATA (DATABASE, USERNAME, PASSWORD, HOST) AND FINALLY INSTALL WORDPRESS...

		__________________________________
			
Ref: https://www.digitalocean.com/community/tutorials/install-wordpress-on-ubuntu?utm_medium=affiliates&utm_source=impact&utm_campaign=357605&utm_content=97660149169c47df9d0fd1f0e5ccc9ea&irgwc=1&irclickid=2FqSWSz%3ADxyNTpPzoKRIEQ4NUkDTtpR5qxq5XU0

