# NGINX Sections
By Jason Yao

## Description
The nginx reverse proxy will serve the satic content from the site directly, without the need to reach the application layer unless the cache object is stale.

## Setup

Make a backup:

```sh
sudo cp /etc/nginx/nginx.conf /etc/nginx/nginx.conf.backup
```

Symlink the [nginx configuration file](nginx.conf) to `/etc/nginx/nginx.conf`:

```sh
sudo ln -s /server/nginx/nginx.conf /etc/nginx/nginx.conf
```

Symlink the [server file](yaoServerMaster) to `/etc/nginx/sites-available`:

```sh
sudo ln -s /server/nginx/yaoServerMaster /etc/nginx/sites-available/yaoServerMaster
```

Symlink the symlink in `/etc/nginx/sites-available` to `/etc/nginx/sites-enabled`:

```sh
sudo ln -s /etc/nginx/sites-available/yaoServerMaster /etc/nginx/sites-enabled/yaoServerMaster
```

## Running

Start:

```sh
sudo service nginx start
```

Stop:

```sh
sudo service nginx stop
```

Restart:

```sh
sudo service nginx restart
```

## Checking log files
Access and error logs will be written to disk, respectively at `/var/log/nginx/access.log` and `/var/log/nginx/error.log`.
You'll need `sudo` privileges to go into the `/var/log/nginx` folder.

To check the last 10 entries quickly:

- The access log:

	- `sudo tail /var/log/nginx/access.log`

- The error log:

	- `sudo tail /var/log/nginx/error.log`

To check the last <k> entries, where n is a positive integer value:

- The access log:

	- `sudo tail -n <k> /var/log/nginx/access.log`

	- E.g.: `sudo tail -n 50 /var/log/nginx/access.log` # Will print the last 50 entries in the access log file

- The error log:

	- `sudo tail -n <k> /var/log/nginx/error.log`

	- E.g.: `sudo tail -n 50 /var/log/nginx/error.log` # Will print the last 50 entries in the error log file
