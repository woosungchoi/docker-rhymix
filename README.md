# docker-rhymix

These are some reasons why use this Docker Compose in your `Rhymix` production environment.

☝️ 2 command to install

⚡ Performance Optimized

🔒 SSL auto-renewed

🆕 Latest docker images and Rhymix

🚧 Phpmyadmin for database administration

🚢 Portainer for docker container management

## Stack

- Ubuntu 20.04 LTS or Centos 8
- Rhymix latest(including rewrite configuration)
- Php7.4 latest docker image(alpine)
- MariaDB latest docker image
- Nginx latest docker image(alpine)
- Certbot latest docker image
- Redis latest docker image(alpine)
- Phpmyadmin latest docker image(fpm-alpine)
- Portainer latest docker image
- Docker
- Docker-compose

## How to use this source ?

Make sure that your `domain` and `www.domain` and `pma.domain` and `port.domain` are pointing to your server IP.

| Type | Name | Content |
| - | - | - |
| A | domain.com | 123.123.123.123 |
| A | pma | 123.123.123.123 |
| A | port | 123.123.123.123 |
| A | www | 123.123.123.123 |

Open `80`,`443` port for connect.

Copy this command below and run it inside your new server. 

# PHP 7.4

### For Ubuntu 20.04 LTS users

```bash
sudo apt update -y && sudo apt upgrade -y && sudo apt install curl git cron -y && sudo apt autoremove -y
```

```bash
curl -o dc https://raw.githubusercontent.com/woosungchoi/docker-rhymix/main/dc && bash dc setup && rm -f dc
```

### For Centos 8 users

```bash
sudo yum -y update && sudo yum install -y curl git crontabs
```

```bash
curl -o dcc https://raw.githubusercontent.com/woosungchoi/docker-rhymix/main/dcc && bash dcc setup && rm -f dcc
```

---

## How do I use this source locally and non SSL on dev environments?

### For Ubuntu 20.04 LTS users

```bash
sudo apt update -y && sudo apt upgrade -y && sudo apt install curl git -y && sudo apt autoremove -y
```

```bash
curl -o dcl https://raw.githubusercontent.com/woosungchoi/docker-rhymix/main/dcl && bash dcl setup && rm -f dcl
```

### For Centos 8 users

```bash
sudo yum -y update && sudo yum install -y curl git
```

```bash
curl -o dccl https://raw.githubusercontent.com/woosungchoi/docker-rhymix/main/dccl && bash dccl setup && rm -f dccl
```

### For Windows 10 WSL2 Ubuntu 20.04 LTS users

Install WSL2 Ubuntu 20.04 LTS and docker

https://www.wsgvet.com/ubuntu/160 , https://www.wsgvet.com/ubuntu/180

```bash
sudo apt update -y && sudo apt upgrade -y && sudo apt autoremove -y
```

```bash
curl -o dcwl https://raw.githubusercontent.com/woosungchoi/docker-rhymix/main/dcwl && bash dcwl setup && rm -f dcwl
```

---

# PHP 8.0

### For Ubuntu 20.04 LTS users

```bash
sudo apt update -y && sudo apt upgrade -y && sudo apt install curl git cron -y && sudo apt autoremove -y
```

```bash
curl -o dc https://raw.githubusercontent.com/woosungchoi/docker-rhymix/main/dc-8.0 && bash dc setup && rm -f dc
```

### For Centos 8 users

```bash
sudo yum -y update && sudo yum install -y curl git crontabs
```

```bash
curl -o dcc https://raw.githubusercontent.com/woosungchoi/docker-rhymix/main/dcc-8.0 && bash dcc setup && rm -f dcc
```

---

## How do I use this source locally and non SSL on dev environments?

### For Ubuntu 20.04 LTS users

```bash
sudo apt update -y && sudo apt upgrade -y && sudo apt install curl git -y && sudo apt autoremove -y
```

```bash
curl -o dcl https://raw.githubusercontent.com/woosungchoi/docker-rhymix/main/dcl-8.0 && bash dcl setup && rm -f dcl
```

### For Centos 8 users

```bash
sudo yum -y update && sudo yum install -y curl git
```

```bash
curl -o dccl https://raw.githubusercontent.com/woosungchoi/docker-rhymix/main/dccl-8.0 && bash dccl setup && rm -f dccl
```

### For Windows 10 WSL2 Ubuntu 20.04 LTS users

Install WSL2 Ubuntu 20.04 LTS and docker

https://www.wsgvet.com/ubuntu/160 , https://www.wsgvet.com/ubuntu/180

```bash
sudo apt update -y && sudo apt upgrade -y && sudo apt autoremove -y
```

```bash
curl -o dcwl https://raw.githubusercontent.com/woosungchoi/docker-rhymix/main/dcwl-8.0 && bash dcwl setup && rm -f dcwl
```

---

## Rhymix Install Configuration

DB : `mysql`

DB server address : `db`

DB server port : `3306`

DB ID : `YOUR DATABASE USERNAME`

DB Password : `YOUR DATABASE PASSWORD`

DB name : `YOUR DATABASE NAME`


## Rhymix Redis cache configuration

Admin panel(관리자 페이지) -> Configuration(설정) -> System configuration(시스템 설정) -> Advanced configuration(고급설정)

Cache enable(캐시 사용) : `redis`

Host(호스트) : `redis`

Port(포트) : `6379`

DB number(DB번호) : `1`

## How to setup automatic execution of upgrade to latest version of Docker image

First, change the `/your/path/to/rhymix/` part of the `docker_upgrade.sh` file to suit your environment.

Then, make this file executable.

```
chmod a+x docker_upgrade.sh
```

And put it in crontab. Change the `/your/path/to/rhymix/` part of the content below.

```
echo "30 12 * * * /your/path/to/rhymix/upgrade.sh >> /var/log/docker_upgrade_cron.log 2>&1" >> mycron && sudo crontab mycron && rm mycron
```

---

## URLs

Rhymix : https://yourdomain.com

Phpmyadmin : https://pma.yourdomain.com

Portainer : https://port.yourdomain.com

---

## Commands

| Commands  | Description  |
|---|---|
| `./dc start`  | Start your containers  |
| `./dc stop`  | Stop all containers  |
| `./dc update`  | Get latest docker images update and restart containers |
