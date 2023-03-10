## Miscellaneous ##

### Docker Container Lifecyle ###

| Purpose      | Command    | Meaning                               |
| -------------|   :---:    |---------------------------------------|
| Conception   | **build**  | **Build** an image from a Dockerfile  |
| Birth        | **run**    | (create+start) a container            |
| Reproduction | **commit** | (persist) a container to a new image  |
|              | & **run**  | Run a new container from an image     |
| Kill         | **kill**   | Kill a running container (SIGKILL)    |
| Wake         | **start**  | Start a stopped container             |
| Death        | **rm**     | Delete a stopped container            |
| Extinction   | **rmi**    | Delete a container image              |


### What is the difference between Docker and Docker Compose? ###

**Docker**

Docker is a tool which is used by developer and operation teams to create and automate the deployment of applications in lightweight containers so that applications can work efficiently in different environments.

![This is an image](/images/docker.png)

**Docker compose**

1. Docker Compose is used for running multiple containers as a single service
2. Here, containers run in isolation but can interact with each other
3. All Docker Compose files are YAML files
4. In Docker Compose, a user can start all the services (containers) using a single command

![This is an image](/images/docker-compose.png)

**Example**

![This is an image](/images/docker-compose-example.png)


### What is different between Docker and Docker-Swarm? ###

You really can’t compare Docker with Docker swarm. Docker is a tool that enables you to use containers, where you could deploy applications into. You could think of it as a very lightweight virtual machine. Docker swarm on the other hand is an orchestration and clustering tool for Docker containers, it uses docker internally. Docker swarm comes in handy if you have dozens to thousands of containers. It manages and schedules these containers. It decides to which container it should route the current request to through load balancing and service discovery.

The correct comparison would be comparing Docker Swarm and Kubernetes, but that’s for another question.

### What is the difference between Docker Compose and Docker Run? ###

Docker Compose is used to run multiple containers as a single service. For example, suppose you had an application that required NGNIX and MySQL, you could create one file which would start both the containers as a service without the need to start each one separately.

Docker runs processes in isolated containers. A container is a process that runs on a host. The host may be local or remote. When an operator executes docker run, the container process that runs is isolated in that it has its own file system, its own networking, and its own isolated process tree separate from the host.

### Microservices ##

[Microservices](https://www.redhat.com/en/topics/microservices/what-are-microservices) - also known as the microservice architecture - is an architectural style that structures an application as a collection of services that are

* Highly maintainable and testable
* Loosely coupled
* Independently deployable
* Organized around business capabilities
* Owned by a small team

The microservice architecture enables the rapid, frequent and reliable delivery of large, complex applications. It also enables an organization to evolve its technology stack. For more details [visit here](https://microservices.io/).


## References

* [Official docker guide](https://docs.docker.com/)
* [Docker cheat sheet](https://github.com/wsargent/docker-cheat-sheet)
* [Geeks for geeks](https://www.geeksforgeeks.org/introduction-to-docker/)
* [Docker compose lamp](https://github.com/harshalone/docker-compose-lamp)
* [Dockerfile & docker-compose](https://www.baeldung.com/ops/docker-dockerfile-docker-compose)

:house: [Home Page](README.md) | [<< Previous Page](Sample-Project.md)
