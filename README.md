# IPv6 SCGI Fano web application example

Example [SCGI](https://python.ca/scgi/protocol.txt) web application using Fano Framework, Pascal web application framework, that demonstrates how to use [IPv6 address](https://fanoframework.github.io/working-with-application#use-ipv6-address).

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

Make sure all requirements are met. Run
```
$ git clone https://github.com/fanoframework/fano-ipv6.git --recursive
$ cd fano-ipv6
$ ./tools/config.setup.sh
$ ./build.sh
$ sudo fanocli --deploy-scgi=ipv6.fano --host="[::1]"
$ ./bin/app.cgi
```

Open internet browser and go to `http://ipv6.fano`. You should see application.
