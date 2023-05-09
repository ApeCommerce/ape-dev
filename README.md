# Ape Dev

The provided [Docker Compose](https://docs.docker.com/compose) stack defines a complete environment for local development.

It is composed of a Node.js container and required services:

- MinIO: Object storage
- MariaDB: Primary database
- Redis: Cache / queues
- MailDev SMTP: Mail proxy

A set of tools is included to ease development. These services are optional and can be commented out in the `docker-compose.yml` file:

- ReDoc: API documentation
- Hoppscotch: HTTP client
- MinIO Console: Object storage manager
- CloudBeaver: Database manager
- Redis Insight: Cache manager
- Bull Dashboard: Queues manager
- MailDev UI: Mail box

To customize local ports on which services are exposed, create a `.env` file:

```
cp .env.default .env
```

Deploy stack:

```
docker compose up -d
```

## Services

| Name           | Local URL             | Docker URL     | User / Password     |
| -------------- | --------------------- | -------------- | ------------------- |
| API            | http://localhost:3000 |                |                     |
| Admin          | http://localhost:3001 |                |                     |
| Store          | http://localhost:3002 |                |                     |
| ReDoc          | http://localhost:4000 |                |                     |
| Hoppscotch     | http://localhost:5000 |                |                     |
| MinIO          | `localhost:6000`      | `minio:9000`   | `root` / `password` |
| MinIO Console  | http://localhost:6001 |                |                     |
| MariaDB        | `localhost:7000`      | `mariadb:3306` | `root` / `password` |
| CloudBeaver    | http://localhost:7001 |                |                     |
| Redis          | `localhost:8000`      | `redis:6379`   |                     |
| Redis Insight  | http://localhost:8001 |                |                     |
| Bull Dashboard | http://localhost:8002 |                |                     |
| MailDev SMTP   | `localhost:9000`      | `maildev:1025` |                     |
| MailDev UI     | http://localhost:9001 |                |                     |

## Development

Get a Node.js container shell:

```
docker compose exec node bash
```

By default, all `ape-` repositories are mounted under Node.js container's working directory. Mounts can be customized in the `docker-compose.yml` file:

| Repository                 | Directory       |
| -------------------------- | --------------- |
| [Ape Commerce](README.md)  | `ape-commerce`  |
| [Ape Framework](README.md) | `ape-framework` |
| [Ape Common](README.md)    | `ape-common`    |
