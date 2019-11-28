# docker-php56-apache

PHP 5.6 / Apache based on official PHP Docker repository
php:5.6.40-apache-stretch

## What is it?

Docker image for PHP-5.6-apache with :
 - mbstring
 - mcrypt
 - pdo_pgsql
 - intl
 - gd
 - ldap
 - opcache
 - memcached
 - soap
 - zip
 - oci8 + pdo_oci
 - dblib + mssql

Timezone is set to _Europe/Paris_.

PHP sessions are stored in *memcached* (see docker-compose.yml).

Apache rewrite mod is enabled.


## Usage

docker-compose.yml :

```
    php56-apache:
      ...
      ports:
        - "80:80"
      volumes:
        - ./apps:/var/www
        - ./logs/apache/:/var/log/apache
        - ./logs/php56-apache/:/var/log/php
      environment:
        - APACHE_RUN_USER=#1000
      networks:
        - backend
      restart: unless-stopped

    memcached:
      image: memcached:1.5-alpine
      ports:
        - "${MEMCACHED_HOST_PORT}:11211"
      depends_on:
        - php56-apache
      networks:
        - backend
      restart: unless-stopped
```
