# About

> Code examples based on Alura's MongoDB course.

## Getting started with Docker

**Creating a container**

```
$ sudo docker run --name mongo-container-name -d mongo
```

**Starting a existing container**

```
$ sudo docker start mongo-container-name
```

**Acessing MongoDB CLI in a container**

```
$ sudo docker exec -it mongo-container-name bash
```
