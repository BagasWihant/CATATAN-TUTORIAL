# to create phpmysql and mysql in docker 

```
version 3.8

services:
  mysql:
    image: mysql:latest
    container_name:mysqlnya
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: DB_NAME
    ports:
      - "3306:3306"
    volumes:
      -mysql_data:/var/lib/mysql

  phpmyadmin:
    image: phpmyadmin/phpmyadmin
    container_name: phpmyadminnya
    links:
      - mysql
    environment:
      PMA_HOST: mysql
      PMA_PORT: 3306
      PMA_ARBITRARY: 1
    restart: always
    ports:
      - "8080:80"

volumes:
  mysql_data:

```
