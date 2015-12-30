# Minecraft Section

## Description

This directory contains two parts, a systemd service to regenerate the minecraft server upon reboot, and the files for the minecraft server itself

## Setup

Symlink the new [systemd service](minecraft.service):

```sh
sudo ln -s /minecraft/minecraft.service /etc/systemd/system/minecraft.service
```

## Managing the service:

### Start:

```sh
sudo service minecraft start
```
### Stop:
```sh
sudo service minecraft stop
```

### Restart:
```sh
sudo service minecraft restart
```
