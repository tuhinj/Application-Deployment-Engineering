::Initial Server SetUp::
- sudo apt updat && sudo apt upgrade -y
- sudo su # Root user
- adduser "usern, fullname, pssword, phonenumber" # add user
- usermod -aG sudo "usern" # user add in sudo group
- apt instlall openssh-server # install ssh server
- ssh "usern"@"user IP" # swap new user

-------------------------------------------------------------------------
::LAMP Stack::
L : Linux (any Linux Distribution)
A : Apache2
M : MySQL
P : PHP


1) Apache2 Install:
- sudo apt update && sudo apt upgrade -y
- sudo apt install apache2
- sudo ufw app list #active application
- sudo ufw allow in "Apache" #Apache allow in firewall rule
- sudo ufw status
** (test apache in browser by "localhost.com or IP address)

2) MySQL Install:
- sudo apt install mysql-server
- sudo mysql_secure_installation
- sudo mysql
- *(CREATE USER'usern'@'localhost' IDENTIFIED WITH mysql_native_password BY 'passw';
GRANT ALL PRIVILEGES ON *.* TO 'usern'@'localhost';)
- mysql> exit

3) PHP Install:
- sudo apt install php libapache2-mod-php php-mysql
- php -v

4) Creating a Virtual Host for your Website:
- sudo mkdir /var/www/your_domain
- sudo chown -R $USER:$USER /var/www/your_domain
- sudo nano /etc/apache2/sites-available/your_domain.conf
** pest >>

<VirtualHost *:80>
    ServerName your_domain
    ServerAlias www.your_domain 
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/your_domain
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

- sudo a2ensite your_domain
- sudo a2dissite 000-default
- sudo apache2ctl configtest
- sudo systemctl reload apache2
- nano /var/www/your_domain/index.html
**pest >>

<html>
  <head>
    <title>your_domain website</title>
  </head>
  <body>
    <h1>Hello World!</h1>

    <p>This is the landing page of <strong>your_domain</strong>.</p>
  </body>
</html>

- http://server_domain_or_IP
- sudo nano /etc/apache2/mods-enabled/dir.conf
**pest >>

<IfModule mod_dir.c>
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>

- sudo systemctl reload apache2

5) Testing PHP Processing on your Web Server:
- nano /var/www/your_domain/info.php
** pest >>

<?php
phpinfo();

- http://server_domain_or_IP/info.php
- sudo rm /var/www/your_domain/info.php

7) Testing Database Connection from PHP (Optional):
- sudo mysql
- mysql> CREATE DATABASE example_database;
- mysql> CREATE USER 'example_user'@'%' IDENTIFIED BY 'password';
- mysql> GRANT ALL ON example_database.* TO 'example_user'@'%';
- mysql> exit
- mysql -u example_user -p
- mysql> SHOW DATABASES;
- mysql> CREATE TABLE example_database.todo_list (
	item_id INT AUTO_INCREMENT,
	content VARCHAR(255),
	PRIMARY KEY(item_id)
);
- mysql> INSERT INTO example_database.todo_list (content) VALUES ("My first important item");
- mysql> SELECT * FROM example_database.todo_list;
- mysql> exit
- mysql> nano /var/www/your_domain/todo_list.php
** pest >> 

<?php
$user = "example_user";
$password = "password";
$database = "example_database";
$table = "todo_list";

try {
  $db = new PDO("mysql:host=localhost;dbname=$database", $user, $password);
  echo "<h2>TODO</h2><ol>"; 
  foreach($db->query("SELECT content FROM $table") as $row) {
    echo "<li>" . $row['content'] . "</li>";
  }
  echo "</ol>";
} catch (PDOException $e) {
    print "Error!: " . $e->getMessage() . "<br/>";
    die();
}

- http://your_domain_or_IP/todo_list.php
- 

