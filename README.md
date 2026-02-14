# Allocella - Infrastructure

This repository will mostly be about docker containerization. I don't know about orchestrastion tho...

## Tech Stack
- Docker
- PostgreSQL v15
    - Containerized
    - Using PostgreSQL v15 (quite lightweight they say)
    - Using standard port for Postgre (5432)
    - Have been made sure to be ready before accepting connections `healthcheck` on [docker_compose.yml](docker_compose.yml)

## Run

### **Prequisities:**
- [Docker](https://www.docker.com/products/docker-desktop/)

### Step-by-Step
Assuming you have cloned or have the repository in local folder.

1. Locate to this _infrastructure_ repository in local directory.
2. Make a `.env` file, and fill in the required information. Use [.env.example](.env.example) for reference.
3. Run `docker-compose up -d`. This will create the Postgre image (database) in detached mode (in background).
    -  To validate if PostgreSQL was created with the right username:
        ```bash
        docker exec -it allocella-postgres psql -U allocella_user -d allocella_db
        ```
    - Type `\du` and press ENTER.
    - If `allocella_user` listed on the table, **variables have worked!**
    - Type `\q` to exit.
