# PHP docker compose develop server

## Under the hood

- php 7.3
- maria db 10.3
- redis 5.05
- nginx latest
- phpmyadmin

## How to use

`$ git clone git@github.com:vt-parhomenko/docker-php-dev-server.git`

You can rename project directory, edit docker-compose.yml file

Set your variables into .env file. For example:

```
XDEBUG_REMOTE_HOST=172.17.0.1
XDEBUG_REMOTE_PORT=9000
XDEBUG_REMOTE_CONNECT_BACK=0
MYSQL_ROOT_PASSWORD=root
MYSQL_DATABASE=db
MYSQL_USER=user
MYSQL_PASSWORD=pass
TZ="Europe/Kiev"
```

`$ docker-compose up`

#Do the great things!
