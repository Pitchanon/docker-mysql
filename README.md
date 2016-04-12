# docker mysql

- [Docker Hub](https://hub.docker.com/r/pitchanon/docker-mysql/)

## Components

- MySQL Server 5.5 (tag: 5.5)
- MySQL Server 5.6 (tag: 5.6)
- MySQL Server 5.7, the latest GA version (tag: 5.7 or latest)

## Running & Building
### Using this container as a base
Use this container as a base for your application. Below is an example Dockerfile:

```
FROM pitchanon/docker-mysql:5.5
... OR ...
5.6, 5.7 or latest
```

##### Add `env_file:` in `docker-compose.yml`

```
mysql:
  build: ./mysql
  ports:
    - 33006:3306
  env_file:
    - ./env/docker.env # environment-specific
```

##### Create file env `docker.env`

```
#docker.env

ENVIRONMENT=docker

MYSQL_ROOT_PASSWORD=123456
MYSQL_PORT_3306_TCP_ADDR=192.168.99.100
MYSQL_PORT_3306_TCP_PORT=33006
```
