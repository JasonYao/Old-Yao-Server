# [Let's Encrypt](https://letsencrypt.org/): Free Automated TLS certificate
By Jason Yao

## Description

We will use LE to automate the generation and deployment of each of our TLS certs, such that I own't have to think about this shit anymore.

## Setup

### Initial build
Go to the [/letsEncrypt](.) directory

```sh
cd /server/letsEncrypt
```

Create a build directory and download the letsencrypt binaries from github, running the update

```sh
git clone https://github.com/letsencrypt/letsencrypt build
cd build
./letsencrypt-auto
```

## Configuration files

Each configuration will will be symlinked to `/etc/letsencrypt/`:

- [yaoGlobalCLI.ini](yaoGlobalCLI.ini) will be symlinked to `/etc/letsencrypt/yaoGlobalCLI.ini`

- [yaoFoundationCLI.ini](yaoFoundationCLI.ini) will be symlinked to `/etc/letsencrypt/yaoFoundationCLI.ini`

- [jasonYaoNetCLI.ini](jasonYaoNetCLI.ini) will be symlinked to `/etc/letsencrypt/jasonYaoNetCLI.ini`

## Running the program
Make sure you are inside of the `build` directory

```sh
./letsencrypt-auto --config /etc/letsencrypt/yaoGlobalCLI.ini --agree-tos certonly
./letsencrypt-auto --config /etc/letsencrypt/yaoFoundationCLI.ini --agree-tos certonly
./letsencrypt-auto --config /etc/letsencrypt/jasonYaoNetCLI.ini --agree-tos certonly
```

## Cron job

The `cron` job is already on the server, and will just do one thing: run the above program once every 60 days,
then send an email about it to the specified email address.
