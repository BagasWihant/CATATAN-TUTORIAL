# install php linux
    sudo apt  install php php-dom php-xml php-common php-cli php-sqlite3

### jika php 8.3 tidak ada       
              
 -      sudo apt-get install ca-certificates apt-transport-https software-properties-common

 -      add-apt-repository ppa:ondrej/php

# install phpmyadmin linux

## install apache    
       sudo apt install apache2
### seting folder `var/www` agar bisa diedit
-       sudo chmod -R 755 /var/www
-       sudo chown -R $USER:$USER /var/www

## mysql server

      sudo apt install mysql-server
## phpmyadmin

       sudo apt install phpmyadmin
## seting user phpmyadmin

-      sudo mysql
-      CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
-      GRANT ALL PRIVILEGES ON mydatabase.* TO 'newuser'@'localhost';
-      GRANT CREATE, ALTER, DROP, INSERT, UPDATE, DELETE, SELECT, REFERENCES, RELOAD on *.* TO 'user'@'localhost' WITH GRANT OPTION; 
-      FLUSH PRIVILEGES;
-      exit;
