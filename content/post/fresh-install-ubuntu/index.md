+++
author = "hophamlam"
title = "Fresh Setup Ubuntu Server"
date = "2022-02-10"
description = "A Personal Guide for quick fresh Ubuntu server setup"
categories = [
    "Cloud", "VPS"
]
tags = [
    "Cloud", "VPS"
]

+++

## Passwordless logging in

### Locate public SSH key

`ls ~/.ssh/id*`

`ssh-copy-id`

### Login as root

`passwd` 

`sudo apt-get update && sudo apt-get -y upgrade`

`sudo nano /etc/hosts`

[When I run a sudo command it says unable to resolve host](https://askubuntu.com/questions/811098/when-i-run-a-sudo-command-it-says-unable-to-resolve-host)

`sudo nano /etc/ssh/sshd_config`

`sudo service ssh restart`

`adduser hophamlam`

`usermod -aG sudo hophamlam`

### Copy key -> Log in without password

`ssh-copy-id hophamlam@`

### Log in as root from user

`sudo -i`

### Disable log in as root from outside ssh

`sudo nano /etc/ssh/sshd_config`

`sudo service ssh restart`

## Install Docker and Docker Compose

`sudo wget https://gist.githubusercontent.com/wdullaer/f1af16bd7e970389bad3/raw/4a5a72aece57e1deca926894e5919f90350c706d/install.sh`

`sh install.sh`
