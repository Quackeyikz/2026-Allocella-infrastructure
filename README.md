# Allocella - Infrastructure

![Docker](https://www.docker.com/app/uploads/2023/08/logo-guide-logos-1.svg)

![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ![Alpine Linux](https://img.shields.io/badge/Alpine_Linux-%230D597F.svg?style=for-the-badge&logo=alpine-linux&logoColor=white)

This is the DATABASE repository. The initial setup you must do will be provided down [here](#how-to-run-the-infrastructure), please read the alternative choice before using this infrastructure. To see the main docs of Allocella, see [Allocella Docs](https://github.com/Quackeyikz/2026-Allocella-docs).

## Tech Stack
- Docker
- Alpine
- PostgreSQL v15
    - Containerized
    - Using PostgreSQL v15 (quite lightweight they say)
    - ~~Using standard port for Postgre (5432)~~ Can adapt to .env
    - Have been made sure to be ready before accepting connections on [docker_compose.yml](docker-compose.yml)

## How to Run The Infrastructure

> ### (Important!)
> You **are not required** to use this infrastructure setup. All you need is a DATABASE. This guide is just providing **one way** to make a database, _although more flexibly_.

If you're sure and ready to proceed, don't forget to get all the requirements.

#### Prequisities:
- [Docker](https://www.docker.com/products/docker-desktop/)

#### Step-by-Step
Assuming you have **cloned** or have the repository in local folder.

1. `cd 2026-Allocella-infrastructure`
2. `cp .env.example .env`
    - Edit the information needed.
3. Run `docker-compose up -d`.
    - This will create the Postgre image (database) in detached mode (in background).
    -  To validate if PostgreSQL was created with the right username:
        ```bash
        docker exec -it allocella-postgres psql -U {your_username} -d {your_db_name}
        ```
    - Type `\du` and press ENTER.
    - If `{your_username}` listed on the table, **variables have worked!**
    - Type `\q` to exit.


## Contributions

It's just me gng, Quackeyikz.
