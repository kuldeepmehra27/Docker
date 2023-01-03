## Docker CLI ##

**1. Docker run**

**Syntax:** *docker run -d --name container_name -e image_params image_name*

Example
```
docker run -d --name mysqldb -e MYSQL_ROOT_PASSWORD=password mysql

docker run -d --name drupal --link mysqldb -p 8080:80 -e MYSQL_USER:root -e MYSQL_PASSWORD:password drupal

docker run -d --name phpmyadmin --link mysqldb:db -p 9090:80 phpmyadmin
```
[Official reference](https://docs.docker.com/engine/reference/commandline/run/)

**2. Docker images**
 - Get all images
   ```
   docker images
   ```
- Remove docker images
  ```
  docker rmi image-name/image-id
  docker rmi -f image-name/image-id (forecfully)
  ```


**3. Docker process status**

- Get list of containers
```
docker ps
  OR
docker container ls
```
- Get list of running as well as stopped container
```
docker ps -a
  OR
docker container ls -a
```

**4. Clear docker cache**
```
docker rmi $(docker images -a -q)
docker system prune -a
```

**5. Docker permission denied error (ubuntu)**
```
sudo chmod 666 /var/run/docker.sock
sudo usermod -aG docker $USER
```

The -it flags will connect the current terminal window to the container's shell

[Official reference](https://docs.docker.com/engine/reference/commandline/docker/)

## Sample Project ##

### Lifecycle

* [`docker create`](https://docs.docker.com/engine/reference/commandline/create) creates a container but does not start it.
* [`docker rename`](https://docs.docker.com/engine/reference/commandline/rename/) allows the container to be renamed.
* [`docker run`](https://docs.docker.com/engine/reference/commandline/run) creates and starts a container in one operation.
* [`docker rm`](https://docs.docker.com/engine/reference/commandline/rm) deletes a container.
* [`docker update`](https://docs.docker.com/engine/reference/commandline/update/) updates a container's resource limits.


:house: [Home Page](README.md) | [Next Page >>](Sample-Project.md)
