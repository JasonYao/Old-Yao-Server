# uWSGI Section

## Description

This directory contains two parts, an Upstart script to regenerate uWSGI at boot, and the configuration files for the uWSGI server itself.

## Systemd service
The [uwsgi.service](uwsgi.service) file will be symlinked to `/etc/systemd/system/uwsgi.service`
