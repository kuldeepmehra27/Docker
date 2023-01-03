
## Sample Project ##

- **Create directory and clone below repository** [Repo Link](https://github.com/kuldeepmehra27/DockerD10)

  ```
  $ git clone https://github.com/kuldeepmehra27/DockerD10.git
  ```
- **Run following command to create container**
  ```
  $ cd DockerD10
  $ docker compose up -d
  ```
After completion you need to open brower and paste this url **http://localhost:8000/web** now install drupal. In database step you need to fill *dbname, dbuser & dbpassword* **drupal10** and *host* **drupal10_db**.

For phpmyadmin you need to visit follow url **http://localhost:9000** *servername* **drupal10_db** *username & password* **drupal10**.

I have attached screentshot for more details.

**How to execute commands on running containers?**
* **For Drupal**
```
$ docker ps

$ docker exec -it drupal10 bash

# drush --version
```
* **For Mariadb**
```
$ docker ps

$ docker exec -it mariadb bash

# mysql -u drupal10 -p
Enter password: drupal10
MariaDB [(none)]> show databases;
```
**Note: You can update db, port & container details in *docker-compose.yml* file.** Before that you need to stop and remove all the containers.

**Visit below url's for image details:**
* [Drupal](https://hub.docker.com/_/drupal)
* [MariaDB](https://hub.docker.com/_/mariadb)
* [PHPMyadmin](https://hub.docker.com/_/phpmyadmin)
* [Adminer](https://hub.docker.com/_/adminer)


**Screentshots:** [Screenshots](Screenshots.md)

We can install drupal using following commands **without Dockerfile & docker-compose.yml** file
```
$ docker run -d --name mysqldb -e MYSQL_ROOT_PASSWORD=password mysql

$ docker run -d --name drupal --link mysqldb -p 8080:80 -e MYSQL_USER:root -e MYSQL_PASSWORD:password drupal
```

:house: [Home Page](README.md) | [<< Previous Page](Docker-CLI.md) | [Next Page >>](Miscellaneous.md)
