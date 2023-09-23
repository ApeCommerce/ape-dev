# Ape Framework development environment

Development environment for [Ape Framework](https://github.com/ApeCommerce/ape-framework) using [Docker Compose](https://docs.docker.com/compose).

It is composed of a Node.js container, recommended Ape Framework dependencies, and development tools:

| Service          | Description       | Docker URL       | Local URL                               |
| ---------------- | ----------------- | ---------------- | --------------------------------------- |
| Node.js          | Dev container     | `node:3000-3009` | [localhost:3000](http://localhost:3000) |
| MariaDB          | Primary database  | `mariadb:3306`   | `localhost:3306`                        |
| MinIO            | Object storage    | `minio:9000`     | `localhost:9000`                        |
| Redis            | Cache, queues     | `redis:6379`     | `localhost:6379`                        |
| MailDev SMTP     | SMTP proxy        | `maildev:1025`   | `localhost:1025`                        |
| ReDoc            | API documentation |                  | [localhost:3010](http://localhost:3010) |
| Hoppscotch       | HTTP client       |                  | [localhost:3011](http://localhost:3011) |
| CloudBeaver      | Database manager  |                  | [localhost:3012](http://localhost:3012) |
| MinIO Console    | Storage manager   |                  | [localhost:3013](http://localhost:3013) |
| Redis Insight    | Cache manager     |                  | [localhost:3014](http://localhost:3014) |
| BullMQ Dashboard | Queues manager    |                  | [localhost:3015](http://localhost:3015) |
| MailDev UI       | Mail box          |                  | [localhost:3016](http://localhost:3016) |

## Setup

Define the project directories to be mounted into the Node.js container by adding volume mounts into `docker-compose.yml`:

```yml
services:
  node:
    volumes:
      - ../hello-ape:/home/node/hello-ape
```

To customize services local ports, create a `.env` file:

```
cp .env.sample .env
```

## Development

Deploy stack:

```
docker compose up
```

Get a shell from the Node.js container:

```
docker compose exec node bash
```
