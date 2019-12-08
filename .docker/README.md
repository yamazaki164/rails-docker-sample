# Rails docker sample

This is a sample of docker with `Ruby on Rails`.

## Description

Containers are below:

- app
- db (postgresql)
- redis

It's for development. Do not use to production.

### Usage

- Build `app` container image

```shell
$ docker-compose build app
```

- Create and start containers

```shell
$ docker-compose up -d
```

- Run `bundle install` in a running `app` container

```shell
$ docker-compose exec app bundle install
```

- Run `yarn install` in a running `app` container

```shell
$ docker-compose exec app yarn install
```

- Drop databases

```shell
$ docker-compose exec app ./bin/rails db:drop
```

- Create databases

```shell
$ docker-compose exec app ./bin/rails db:create
```

- Stop containers

```shell
$ docker-compose stop
```

- Remove containers

```shell
$ docker-compose rm
```

- List volumes

```shell
$ docker volume ls
```

- Remove volume

```shell
$ docker volume rm [your_volume_name]
```

- Remove all unused local volumes

```shell
$ docker volume prune
```
