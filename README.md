# Ape Dev Stack

The included [Docker Compose](https://docs.docker.com/compose) stack defines a complete environment for local development.

It is composed of a Node.js container, recommended Ape Framework's dependencies and development tools:

| Service          | Description       | Local URL                               | Docker URL     |
| ---------------- | ----------------- | --------------------------------------- | -------------- |
| API              |                   | [localhost:3000](http://localhost:3000) |                |
| Admin            |                   | [localhost:3001](http://localhost:3001) |                |
| Store            |                   | [localhost:3002](http://localhost:3002) |                |
| ReDoc            | API documentation | [localhost:4000](http://localhost:4000) |                |
| Hoppscotch       | HTTP client       | [localhost:5000](http://localhost:5000) |                |
| MariaDB          | Primary database  | `localhost:6000`                        | `mariadb:3306` |
| CloudBeaver      | Database manager  | [localhost:6001](http://localhost:6001) |                |
| MinIO            | Object storage    | `localhost:7000`                        | `minio:9000`   |
| MinIO Console    | Storage manager   | [localhost:7001](http://localhost:7001) |                |
| Redis            | Caching, queueing | `localhost:8000`                        | `redis:6379`   |
| Redis Insight    | Cache manager     | [localhost:8001](http://localhost:8001) |                |
| BullMQ Dashboard | Queues manager    | [localhost:8002](http://localhost:8002) |                |
| MailDev SMTP     | SMTP proxy        | `localhost:9000`                        | `maildev:1025` |
| MailDev UI       | Mail box          | [localhost:9001](http://localhost:9001) |                |

## Setup

To customize local ports on which services are exposed, create a `.env` file:

```
cp .env.sample .env
```

Deploy stack:

```
docker compose up -d
```

## Development

Get a shell from Node.js container:

```
docker compose exec node bash
```

The Node.js service is configured to mount Ape repositories into its container's working directory:

| Repository                                                    | Local directory    | Container directory        |
| ------------------------------------------------------------- | ------------------ | -------------------------- |
| [Ape Commerce](https://github.com/ApeCommerce/ape-commerce)   | `../ape-commerce`  | `/home/node/ape-commerce`  |
| [Ape Framework](https://github.com/ApeCommerce/ape-framework) | `../ape-framework` | `/home/node/ape-framework` |
