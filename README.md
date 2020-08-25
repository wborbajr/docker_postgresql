![Docker](https://github.com/wborbajr/docker_postgresql/blob/master/docker.jpeg)

## Downloading

```bash
git clone https://github.com/wborbajr/docker_postgresql.git
cd docker_postgresql
```

## PostgreSQL

Before bring container up, please change environment settings at **.env**

```
# PostgreSQL
POSTGRES_USER=xxx
POSTGRES_PASSWORD=xxx
POSTGRES_DB=xxx

# PgAdmin
PGADMIN_DEFAULT_EMAIL=xxx
PGADMIN_DEFAULT_PASSWORD=xxx
PGADMIN_LISTEN_PORT=xxx
```

## Database

All databases will be saved locally at data folder **./data/**

**PS:** If you decided to change folders name or path, please, remember to modify the entry **volumes** at **docker-compose.yaml**

```
volumes:
    - ./data/dbdata:/var/lib/postgresql/data:rw
```

## Port

MariaDB will expose port **3254**, so remember to configure your MySQL Client to connect at **_Port: 3254_**

You can change it at **docker-compose.yaml** for your own propose.

## To execute

### Just PostgreSQL

```bash
docker-compose up -d database
```

Or you can run using Makefile

```bash
make up-db
```

### Bringing up PostgreSQL and PGAdmin-4

```bash
docker-compose up -d
```

Or you can run using Makefile

```bash
make up-all
```

## To stop

### Stopping Development environment

```bash
docker-compose down
```

Or you can run using Makefile

```bash
make down
```

## Configuration

You can setup your own configurations just creating file into **config** folder.

After setup your own PostgreSQL configuration, don't forget to enable at **docker-compose.yaml** at **volumes** section to read your configuration file, removing comment tag.

## Checking status

```bash
docker-compose ps
```
