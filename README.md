# docker-rhymix

These are some reassons why use this Docker Compose in your production environment.

☝️ 2 command to install

⚡ Performance Optimized

🔒 SSL auto-renewed

## Stack

- Ubuntu 20.04 LTS
- Php7.4 latest docker image(alpine)
- MariaDB latest docker imgae
- Nginx latest docker image(alpine)
- Letsencrypt latest docker image
- Redis lastest docker image(alpine)
- Phpmyadmin latest docker image(fpm-alpine)
- Portainer latest docker image
- Docker
- Docker-compose

## How to use this source ?

Then copy this command below and **change the mydomain.com to your domain** and **change the email@email.com to your email address** and run it inside your new server. Make sure that your domain is pointing to your server IP.

```bash
sudo apt update -y && sudo apt upgrade -y && sudo apt install curl git -y && sudo apt autoremove -y
curl -s https://raw.githubusercontent.com/woosungchoi/docker-rhymix/stage/dc | bash -s setup mydomain.com email@email.com
```

## Commands

| Commands  | Description  |
|---|---|
| `./dc start`  | Start your containers  |
| `./dc stop`  | Stop all containers  |
| `./dc update`  | Get Ghost updates and restart containers |
