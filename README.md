# App-Wallabag

## First Time Prerequisites

1. `rm ./Data/mysql/.gitkeep`
2. Run [Traefik](https://github.com/HackingServerHomelab/App-Traefik)

## Running the Containers

1. Update the following lines in [docker-compose.yml](./Docker/docker-compose.yml)
    * `MYSQL_ROOT_PASSWORD=changeme`
    * `SYMFONY__ENV__DATABASE_PASSWORD=changeme`
    * `SYMFONY__ENV__MAILER_HOST=127.0.0.1`
    * `SYMFONY__ENV__MAILER_USER=~`
    * `SYMFONY__ENV__MAILER_PASSWORD=~`
    * `SYMFONY__ENV__FROM_EMAIL=wallabag@example.com`
    * `SYMFONY__ENV__DOMAIN_NAME=https://example.com`
    * `MYSQL_ROOT_PASSWORD=changeme`
2. Update the following volumes in [docker-compose.yml](./Docker/docker-compose.yml)
    * `../Data/images:/var/www/wallabag/web/assets/images`
    * `../Data/mysql:/var/lib/mysql`
3. Update the Traefik host label in [docker-compose.yml](./Docker/docker-compose.yml)
    * ``"traefik.http.routers.wallabag.rule=Host(`localhost`)"``
4. Run `docker-compose -f ./Docker/docker-compose.yml up -d`

## First Time Setup

1. Visit <https://your-ip>
2. Log in with the default credentials `wallabag:wallabag`
