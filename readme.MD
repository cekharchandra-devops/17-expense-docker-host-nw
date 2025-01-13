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
o/p:
```
        "Networks": {
                "host": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "MacAddress": "",
                    "DriverOpts": null,
                    "NetworkID": "f1f5ed50b0716e890b52749aec4e6ed9014acf207ff9f41d6c9da72b755b29d6",
                    "EndpointID": "d975e2c4d69f208e5aa2adfa2af848f1edad360cea7008ef2542489f9b61211c",
                    "Gateway": "",
                    "IPAddress": "",
                    "IPPrefixLen": 0,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "DNSNames": null
                }
            }
        }
    }

```
No IP address is assigned for container. 
