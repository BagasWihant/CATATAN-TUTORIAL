# install php linux
    sudo apt  install php php-dom php-xml php-common php-cli php-sqlite3

# install phpmyadmin linux

- install apache
    
       sudo apt install apache2
- mysql server

      sudo apt install mysql-server
- phpmyadmin

       sudo apt install phpmyadmin
- seting user phpmyadmin

      sudo mysql

      CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';

      GRANT ALL PRIVILEGES ON mydatabase.* TO 'newuser'@'localhost';

      GRANT CREATE, ALTER, DROP, INSERT, UPDATE, DELETE, SELECT, REFERENCES, RELOAD on *.* TO ''@'localhost' WITH GRANT OPTION;
  
      FLUSH PRIVILEGES;

      exit;
