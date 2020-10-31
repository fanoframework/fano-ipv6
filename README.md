# IPv6 SCGI Fano web application example

Example [SCGI](https://python.ca/scgi/protocol.txt) web application skeleton using Fano Framework, Pascal web application framework, that demonstrates how to use IPv6 address.

This project is generated using [Fano CLI](https://github.com/fanoframework/fano-cli)
command line tools to help scaffolding web application using Fano Framework.

## Requirement

- Linux or FreeBSD
- [Free Pascal](https://www.freepascal.org/) >= 3.0
- Web Server ([Apache with mod_proxy_scgi](https://httpd.apache.org/docs/current/mod/mod_proxy_scgi.html), nginx)
- [Fano CLI](https://github.com/fanoframework/fano-cli)
- Web Server (Apache, nginx)
- Administrative privilege for setting up virtual host

## Installation

### TLDR
Make sure all requirements are met. Run
```
$ git clone https://github.com/fanoframework/fano-ipv6.git --recursive
$ cd fano-ipv6
$ ./tools/config.setup.sh
$ ./build.sh
$ sudo fanocli --deploy-scgi=ipv6.fano
$ ./bin/app.cgi
```

## Run

Edit `/etc/apache2/sites-available/ipv6.fano.conf` and replace

```
ProxyPassMatch ^/(.*)$ scgi://127.0.0.1:20477
```

with

```
ProxyPassMatch ^/(.*)$ scgi://[::1]:20477
```
Reload Apache,

```
$ sudo systemctl reload apache2
```
Open internet browser and go to `http://ipv6.fano`. You should see application.
