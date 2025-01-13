# Docker Networking

1. host --> containers communicate with each other using port on same docker host
2. bridge --> default docker network
3. overlay networking --> communication between containers running on different docker hosts

host:
* containers using host n/w will not get IP address. they use host IP address and unique port for communication.

ex:
    mysql running port 3306
    backend service running on 8080
    frontend service running on 80

```
docker run -d --name mysql --network host mysql:v1
docker inspect mysql
```

