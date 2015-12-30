# Let's Encrypt: Free Automated TLS certificate

[website](https://letsencrypt.org/)

## Description

We will use LE to automate the generation and deployment of each of our TLS certs, such that I own't have to think about this shit anymore.

## Running the program

Appreciate the work into figuring out from scratch how the hell to make this into an easily executable one liner

```sh
./letsencrypt-auto --config /etc/letsencrypt/yaoGlobalCLI.ini --agree-tos certonly
./letsencrypt-auto --config /etc/letsencrypt/yaoFoundationCLI.ini --agree-tos certonly
./letsencrypt-auto --config /etc/letsencrypt/jasonYaoNetCLI.ini --agree-tos certonly
```

## Cron job TODO

The `cron` job is already on the server, and will just do one thing: run the above program once every 60 days,
then send an email about it to the omega email address.

## Configuration files

Each configuration will will be symlinked to `/etc/letsencrypt/`:

- [yaoGlobalCLI.ini](yaoGlobalCLI.ini) will be symlinked to `/etc/letsencrypt/yaoGlobalCLI.ini`

- [yaoFoundationCLI.ini](yaoFoundationCLI.ini) will be symlinked to `/etc/letsencrypt/yaoFoundationCLI.ini`

- [jasonYaoNetCLI.ini](jasonYaoNetCLI.ini) will be symlinked to `/etc/letsencrypt/jasonYaoNetCLI.ini`
