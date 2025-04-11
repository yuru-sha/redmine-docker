# redmine-docker

This project provides a simple way to run Redmine with MySQL using Docker Compose.

## Usage

### Prerequisites

*   Docker
*   Docker Compose

### Setup

1.  Clone this repository:
    ```bash
    git clone https://github.com/yuru-sha/redmine-docker.git
    cd redmine-docker
    ```
2.  Create a `.env` file from the example:
    ```bash
    cp .env.example .env
    ```
3.  Edit the `.env` file and set your desired database credentials.

### Running Redmine

Start the containers:
```bash
docker-compose up -d
```

Redmine will be accessible at http://localhost:3000.

### Stopping Redmine

```bash
docker-compose down
```

### Removing Data

To remove the database and file data, delete the `mysql_data` and `redmine_data` directories:
```bash
docker-compose down -v # Stops containers and removes volumes defined in docker-compose.yml
rm -rf mysql_data redmine_data
```
**Caution:** This will permanently delete all your Redmine data.

## .env Configuration

The `.env` file is used to configure the MySQL database credentials. Copy `.env.example` and modify the values:

*   `MYSQL_DATABASE`: The name of the MySQL database for Redmine.
*   `MYSQL_ROOT_PASSWORD`: The password for the MySQL root user.
*   `MYSQL_USER`: The username for Redmine to connect to MySQL.
*   `MYSQL_PASSWORD`: The password for the Redmine MySQL user.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details. (Note: LICENSE file needs to be created)
