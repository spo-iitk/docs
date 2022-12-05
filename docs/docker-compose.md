---
title : docker-compose
layout : default
nav_order: 8
---

##docker-compose.yaml

```yaml
version: "3.5"

services:
  database:
        ...
  server:
        ...

```
- creates 2 services, that are basically docker images.
- one is for the database and other for the server

##### database image
```yaml
database:
    image: postgres
        restart: always
        environment:
            - POSTGRES_USER=postgres
            - POSTGRES_PASSWORD=postgres
        ports:
            - "5432:5432"
        volumes:
            - ./container/init.sql:/docker-entrypoint-initdb.d/init.sql
            - data:/var/lib/postgresql/data
```
- `image:` standard docker image for postgres
- `enviroment:` setting up environment variables for initializing the postgres db
- `ports:` standard mapping of ports
- `volumes:` standard way of initializing so that data persists even when the container is made to restart.

##### server image
```yaml
server:
    build:
        context: .
        dockerfile: container/Dockerfile
    restart: always
    depends_on:
        - database
    networks:
        - default
    ports:
        - "80"
```
* `build:`
    - `context:` specifies the directory's relative location that is to be containarized
    - `dockerfile:` location of the [Dockerfile]() that contains config settings for the image to be built
* `depends_on:` depends on the image of `database` on the container
* `networks & ports` standard configuration

```yaml
volumes:
  data:
```
- this creates a memory space outside the container that will be mapped with the database inside the container for the purpose of making the data persist even when the container is made to restart.
- the mapping is shown with this line of code : `data:/var/lib/postgresql/data` .

```yaml
# network with subnet configuration
networks:
  default:
      driver: bridge
      ipam:
          driver: default
          config:
              - subnet: "192.168.3.0/24"
                # gateway: "192.168.3.1"
```
- this is a standard code to limit the choice of IP-addresses that our container takes.
- the subnet range is specified by `- subnet: "192.168.3.0/24"`

#### REFERENCES
- [understading subnet range](https://www.freecodecamp.org/news/subnet-cheat-sheet-24-subnet-mask-30-26-27-29-and-other-ip-address-cidr-network-references/)
- [Docker](https://docs.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
