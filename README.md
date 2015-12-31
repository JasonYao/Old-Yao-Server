# Yao-Server

By Jason Yao

## Description
An umbrella repository for all things pertaining to the Yao server, and any of its services

## Overview

### [Letsencrypt](letsEncrypt)
An automated way to request and install TLS certificates.

### [Nginx](nginx)
An extremely fast and robust reverse proxy server used to serve static content, all other requests are sent upstream if a cached version is not available.

### [uWSGI](uwsgi)
The python web server that is the entrance to the application layer of each of the services in [web](web) are being run.

### [Web](web)
The server actively serves content for the following domains:

[Active Development] [Yao Global Website](https://github.com/JasonYao/Yao-Global)

[Active Development] [Yao Foundation Website](https://github.com/JasonYao/Yao-Foundation)

### [Minecraft](minecraft)
All files and services pertaining to the management of the minecraft server.

## Setup

Initial download & submodule setup:

`git clone --recursive https://www.github.com/JasonYao/Yao-Server.git`

Update all submodules to their latest respective HEADs

`git submodule update --remote`

## License
This repository is licensed under the GPL GNU v2 license file, as described [here](LICENSE)
