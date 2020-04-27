# Adonis fullstack application

This is the fullstack boilerplate for AdonisJs, it comes pre-configured with.

1. Bodyparser
2. Session
3. Authentication
4. Web security middleware
5. CORS
6. Edge template engine
7. Lucid ORM
8. Migrations and seeds

## PostgreSQL Docker

- Getting the necessary images:
    - `docker pull postgres`
    - `docker pull dpage/pgadmin4`

- Creating a network to execute the containers
    - `docker network create --driver bridge postgres-network`

- Creating a container to run a PostgreSQL instance and to run pgAdmin 4
    ```
    docker run --name db-postgres --network=postgres-network -e "POSTGRES_PASSWORD=postgres" -p 5432:5432 -v /home/matheus/Desenvolvimento/PostgreSQL:/var/lib/postgresql/data -d postgres
    ```
    ```
    docker run --name client-pgadmin --network=postgres-network -p 15432:80 -e "PGADMIN_DEFAULT_EMAIL=matheusmoreira.g6@gmail.com" -e "PGADMIN_DEFAULT_PASSWORD=postgres" -d dpage/pgadmin4
    ```

- Accessing pgAdmin4: `http://localhost:15432`
> Use PGADMIN_DEFAULT_EMAIL and PGADMIN_DEFAULT_PASSWORD to login

- Steps to configure pgAdmin4:

![](./img-pg-conf/pg0.png =50x)

## Start

Starting AdonisJS server

```bash
adonis serve --dev
```

## Setup

Use the adonis command to install the blueprint

```bash
adonis new yardstick
```

or manually clone the repo and then run `npm install`.


### Migrations

Run the following command to run startup migrations.

```js
adonis migration:run
```
