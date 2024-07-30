# tutorial-pgbouncer
Dockerised PgBouncer example

## What is PgBouncer?

> PgBouncer is a connection pooler for PostgreSQL. It reduces performance overhead by rotating client connections to PostgreSQL databases. It supports PostgreSQL databases located on different hosts.

## Why use Bitnami PgBouncer?

The official documentation of PgBouncer can be accessed <a href="https://www.pgbouncer.org/install.html">here</a>. 

Since we’ve dockerised our PostgreSQL database, we prefer pulling the <a href="https://github.com/bitnami/containers/blob/main/bitnami/pgbouncer/README.md">Bitnami PgBouncer Docker Image</a> as it comes pre-configured with defaults.

## Setup

### Step 1: Configure PgBouncer in `docker-compose.yml`

1. Include a pgbouncer service in your `docker-compose.yml` in accordance with the sample provided in this repo.
2. Create a `.env` file in the same directory to store your env variables securely. Populate it with the following configuration:
   
   ```
   CONTAINER_NAME=container_name
   VOLUME_PATH=volume_path
   POSTGRESQL_USER=db_username
   POSTGRESQL_PASSWORD=db_password
   POSTGRESQL_DB=db_name
   POSTGRESQL_PORT=5432
   ```

### Step 2: Start the Container

1. SSH into the staging environment.
2. Navigate to the directory containing your `docker-compose.yml` . Ensure that a `.env` file is set up in the staging environment.
3. Run `docker-compose up -d`.
4. Verify that the images are running correctly.
   
   ```
   docker ps
   ```
6. Have your application’s backend to connect to PgBouncer on port 6432 instead of the PostgreSQL server.
7. Verify that the connection is successful.
   
   ```
   docker logs <pgbouncer_image_name>
   ```

## Demo

*insert yt vid*
