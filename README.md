## Dockerize Laravel 11, PHP 8.3, MySQL, PhpMyAdmin, Nginx, PostgreSQL, PgAdmin 


#### Create an ``.env`` file and store the database information
```
DB_CONNECTION=mysql
DB_HOST=mysql // 
DB_PORT=3301
DB_DATABASE=your_db
DB_USERNAME=your_db_user
DB_PASSWORD=your_db_password
```

#### Run docker compose build
```
docker compose build

# build without cache
docker compose build --no-cache
```

#### Run docker compose up
```
docker compose up

# run on detached mode
docker compose up -d
```
- Webserver - http://localhost:9001
- PhpMyAdmin: http://localhost:8081
- MySql - port 3301

#### Check running docker containers
```
docker ps

# see all containers
docker ps -a
```


### Migration
```
docker compose exec php bash

php artisan migrate
```

### PostgreSQL and PgAdmin
 - Store postgres information in `.env` and remove/comment mysql information
    ```
    DB_CONNECTION=pgsql
    DB_HOST=postgres
    DB_PORT=5434
    DB_DATABASE=postgres
    DB_USERNAME=postgres
    DB_PASSWORD=postgres
    ```
- Uncomment the #PostgreSQL and #pgadmin services in `docker-compose.yml` . Comment #MySQL and #phpMyAdmin services

