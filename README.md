
# Docker Compose Project: MySQL and Adminer

This project is a simple Docker Compose setup to run a MySQL database and Adminer as the database manager. It provides a quick way to deploy a database with the ability to visualize and manage it through Adminer.

## Requirements

- Installed [Docker](https://docs.docker.com/get-docker/)
- Installed [Docker Compose](https://docs.docker.com/compose/install/)

## How to Run the Project

1. **Clone this repository** to your local environment:
   ```bash
   git clone git@github.com:robovarga/local-db-stack.git
   cd local-db-stack
   ```

2. **Run Docker Compose** with the following command:
   ```bash
   docker compose up -d
   ```

   This command will start two containers:
   - **Adminer**: a lightweight database management tool available at `http://localhost:8080`
   - **MySQL**: the MySQL 8 database, which can be accessed via `localhost:3306`

3. **Access Adminer**:
   - Go to `http://localhost:8080` in your web browser.
   - Log in with the following credentials:
     - **System**: `MySQL`
     - **Server**: `db` (use this name to connect Adminer to the database)
     - **Username**: `root`
     - **Password**: `secret_password`

## Volumes

- The MySQL data is persisted in the `_mysql-data` directory on your host machine, so the data remains even if the containers are stopped or removed.

## Stopping the Services

To stop the running containers, run:

```bash
docker compose down
```

This will stop and remove the containers but keep the MySQL data intact because of the volume.

## Notes

- Make sure port `3306` (MySQL) and `8080` (Adminer) are not being used by other services on your machine.
- You can modify the environment variables and the `docker-compose.yml` file to suit your needs.

## Author

- **Róbert Varga** – Creator of this project
