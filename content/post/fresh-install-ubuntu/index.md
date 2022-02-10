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


## Locate your public *SSH* key.

`ls ~/.ssh/id*`

`ssh-copy-id`

## login as root

`passwd` 

`sudo apt-get update && sudo apt-get -y upgrade`

`sudo nano /etc/hosts`

[When I run a sudo command it says unable to resolve host](https://askubuntu.com/questions/811098/when-i-run-a-sudo-command-it-says-unable-to-resolve-host)

`sudo nano /etc/ssh/sshd_config`

`sudo service ssh restart`

`adduser hophamlam`

`usermod -aG sudo hophamlam`

copy key

`ssh-copy-id hophamlam@`

log in as root from user

`sudo -i`

disable log in as root from outside ssh

`sudo nano /etc/ssh/sshd_config`

`sudo service ssh restart`