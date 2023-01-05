## Docker CLI  **[Official reference](https://docs.docker.com/engine/reference/commandline/docker/)**

**Check docker & docker compose version**
```
$ docker version

$ docker compose version
```

**Docker pull** 

The 'docker pull' is a Docker command to download a Docker image or a repository locally on the host from a public or private registry. When we run any container and the specified Docker image is not present locally then it first pulls it from the registry. Most of the time images are downloaded from a public registry that is 'hub.docker.com' when we create our own custom Docker images as we use the official Docker image as a base image. For more details [visit here](https://www.educba.com/docker-pull/).

**Syntax:** *docker pull [OPTIONS] NAME[:TAG|@DIGEST]*

Example
```
$ docker pull ubuntu
$ docker pull drupal
```

**1. Docker run** [Official reference](https://docs.docker.com/engine/reference/commandline/run/)

The docker run command creates a container from a given image and starts the container using a given command. It is one of the first commands you should become familiar with when starting to work with Docker.

**Syntax:** *docker run -d --name container_name -e image_params image_name*

Example
```
$ docker run -d --name mysqldb -e MYSQL_ROOT_PASSWORD=password mysql

$ docker run -d --name drupal --link mysqldb -p 8080:80 -e MYSQL_USER:root -e MYSQL_PASSWORD:password drupal

$ docker run -d --name phpmyadmin --link mysqldb:db -p 9090:80 phpmyadmin
```

**2. Docker images**
 - Get all images
   ```
   $ docker images
   ```
- Remove docker images
  ```
  $ docker rmi image-name/image-id
  $ docker rmi -f image-name/image-id (forecfully)
  ```

**3. Docker process status**

- Get list of containers
```
$ docker ps
  OR
$ docker container ls
```
- Get list of running as well as stopped container
```
$ docker ps -a
  OR
$ docker container ls -a
```
**4. Docker exec**

If you need to start an interactive shell inside a Docker Container, perhaps to explore the filesystem or debug running processes, use docker exec with the -i and -t flags.
The -i flag keeps input open to the container, and the -t flag creates a pseudo-terminal that the shell can attach to. These flags can be combined like this:

**Syntax:** *docker exec -it container-name/container-id bash OR /bin/bash OR sh*

```
$ docker exec -it drupal10 bash 
  OR
$ docker exec -it drupal10 /bin/bash
  OR
$ docker exec -it da5eecf752fa bash

$ docker exec drupal10 ls
```

**5. Other useful commands**
* Get the detail about container
```
  $ docker inspect container-name
  $ docker inspect container-name 2>&1 | grep IPAddress
```
* Stop container
```
  $ docker stop container-name or container-id
```
* Remove container
```
  $ docker rm container-name or container-id
```
* Build command
```
$ docker build -t name_of_image .
```
* strconv.Atoi: parsing "": invalid syntax
```
$ docker compose down --remove-orphans
```

**6. Clear docker cache**
```
$ docker rmi $(docker images -a -q)
$ docker system prune -a
```

**7. Docker permission denied error (ubuntu)**
```
$ sudo chmod 666 /var/run/docker.sock
$ sudo usermod -aG docker $USER
```


:house: [Home Page](README.md) | [<< Previous Page](README.md) | [Next Page >>](Sample-Project.md)
