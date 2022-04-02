+++
author = "hophamlam"
title = "Fresh Setup Ubuntu Server"
date = "2022-02-10"
description = "A very personal guide for fresh Ubuntu server setup"
categories = [
    "Cloud", "VPS"
]
tags = [
    "Cloud", "VPS"
]

+++

# Passwordless logging in

## Locate public SSH key

```ls ~/.ssh/id*```

```cat ~/.ssh/id_rsa.pub```

```ssh-copy-id```

## Login as root

```passwd```

```sudo apt-get update && sudo apt-get -y upgrade```

```sudo nano /etc/hosts```

[When I run a sudo command it says unable to resolve host](https://askubuntu.com/questions/811098/when-i-run-a-sudo-command-it-says-unable-to-resolve-host)

```sudo nano /etc/ssh/sshd_config```

```sudo service ssh restart```

```adduser hophamlam```

`usermod -aG sudo hophamlam`

## Copy key -> Log in without password

```ssh-copy-id hophamlam@```

## Log in as root from user

```sudo -i```

## Disable log in as root from outside ssh

```sudo nano /etc/ssh/sshd_config```

```sudo service ssh restart```

## 

```sudo nano /path/to/your/known_hosts;```

Delete relevant line (in your example that would be line 3)

# Install Docker and Docker Compose

```sudo wget https://gist.githubusercontent.com/wdullaer/f1af16bd7e970389bad3/raw/4a5a72aece57e1deca926894e5919f90350c706d/install.sh```

```sh install.sh```

# Install Portainer

```docker volume create portainer_data```

```docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:2.11.1```

```port 9443```

# Instal Proxy Manager

``` bash
version: '3'
services:
  app:
    image: 'jc21/nginx-proxy-manager:latest'
    restart: unless-stopped
    ports:
      - '80:80'
      - '81:81'
      - '443:443'
    volumes:
      - ./data:/data
      - ./letsencrypt:/etc/letsencrypt

```
