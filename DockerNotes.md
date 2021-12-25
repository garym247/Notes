# Basics

Dockerfile

```
FROM <base image>:<version>
WORKDIR /app
COPY <local> <destination>
RUN
COPY
ENV
CMD
```

There can only be one CMD per dockerfile

.dockerignore

```docker build -t <tag name> <path to docker file>```
reads the contents of the given docker file


A container is a running instance of an image.

docker-compose.yml

version: '3'
services:
  web:






  a
# Image Commands

```docker build``` 

```docker push <image name>```

```docker pull <image name>```

```docker run <image name>```

-p  for port forwarding

# Container Commands

Recommended 1 process per container

```docker ps```

```docker start <container id>```

```docker stop <container id>```

```docker logs <container id>```

```docker exec -it <container id>```


```docker compose <yml file>```

docker compose up

# Debugging

Docker desktop is quite handy for debugging containers

# Python Containers

# WebAPI Containers
