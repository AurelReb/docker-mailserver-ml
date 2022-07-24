# Docker mailserver with mailing list

This is a bundle of [docker-mailserver](https://github.com/docker-mailserver/docker-mailserver)
and [docker-mailman](https://github.com/maxking/docker-mailman) pre-configured
to work together out of the box.

## Getting started

To run the mail server, you first have to change the `docker-compose.yml` by
replacing all elements marked with `CHANGE THIS` to match your needs. Then
change the `mailserver.env` file to custom the mailserver settings (please check
the [official doc](https://docker-mailserver.github.io/docker-mailserver/edge/config/environment/) for more information).

After your configuration is ready, please run the following commands:
```bash
sudo mkdir -p /opt/mailman/core
sudo mkdir -p /opt/mailman/web
docker-compose up
```
Once every service started correctly (or exited for some), you can stop the
`docker-compose`.
Run the following commands:
```bash
sudo cp postfix-main.cf ./config/
docker-compose up -d
./setup.sh email add <user@domain> [<password>]
```
Everything should be good. Please check the official documentation for
[docker-mailserver](https://docker-mailserver.github.io/docker-mailserver/edge/) and [docker-mailman](https://github.com/maxking/docker-mailman) for more information about the setup and for
troubleshooting 
