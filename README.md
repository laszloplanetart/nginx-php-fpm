## Overview

A fork of [https://hub.docker.com/r/richarvey/nginx-php-fpm/](https://hub.docker.com/r/richarvey/nginx-php-fpm/)

This is a Dockerfile/image to build a container for nginx and php-fpm, with a focus on being used behind a proxy and to be able to log to stdout without the php-fpm prefix.

It includes preparing nginx logs for ingestion into analytics services by formatting the logs as json.

No access logging when reaching `/ping`, to prevent redundant logging of successful health checks.

If you have improvements or suggestions please open an issue or pull request on the GitHub project page.

### Versioning
| Docker Tag | Git Release | Nginx Version | PHP Version | Alpine Version |
|-----|-------|-----|--------|--------|
| latest/1.0.0 | Master Branch |1.14.0 | 7.3.1 | 3.8 |

For other tags please see: [versioning](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/versioning.md)

### Links
- [https://github.com/vegandev/nginx-php-fpm](https://github.com/vegandev/nginx-php-fpm)
- [https://registry.hub.docker.com/u/vegandev/nginx-php-fpm/](https://registry.hub.docker.com/u/vegandev/nginx-php-fpm/)

## Quick Start
To pull from docker hub:
```
docker pull vegandev/nginx-php-fpm:latest
```
### Running
To simply run the container:
```
sudo docker run -d vegandev/nginx-php-fpm
```
To dynamically pull code from git when starting:
```
docker run -d -e 'GIT_EMAIL=email_address' -e 'GIT_NAME=full_name' -e 'GIT_USERNAME=git_username' -e 'GIT_REPO=github.com/project' -e 'GIT_PERSONAL_TOKEN=<long_token_string_here>' vegandev/nginx-php-fpm:latest
```

You can then browse to ```http://<DOCKER_HOST>``` to view the default install files. To find your ```DOCKER_HOST``` use the ```docker inspect``` to get the IP address (normally 172.17.0.2)

For more detailed examples and explanations please refer to the documentation.
## Documentation

- [Building from source](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/building.md)
- [Versioning](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/versioning.md)
- [Config Flags](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/config_flags.md)
- [Repository layout / webroot](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/repo_layout.md)
 - [webroot](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/repo_layout.md#src--webroot)
- [User / Group Identifiers](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/UID_GID_Mapping.md)
- [Custom Nginx Config files](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/nginx_configs.md)
 - [REAL IP / X-Forwarded-For Headers](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/nginx_configs.md#real-ip--x-forwarded-for-headers)
- [Scripting and Templating](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/scripting_templating.md)
 - [Environment Variables](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/scripting_templating.md#using-environment-variables--templating)
- [PHP Modules](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/php_modules.md)
- [Logging and Errors](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/logs.md)

## Guides
- [Running in Kubernetes](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/guides/kubernetes.md)
- [Using Docker Compose](https://github.com/vegandev/nginx-php-fpm/blob/master/docs/guides/docker_compose.md)
