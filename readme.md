# Lumen PHP Framework with Docker/Docker-Compose

[![Build Status](https://travis-ci.org/laravel/lumen-framework.svg)](https://travis-ci.org/laravel/lumen-framework)
[![Total Downloads](https://poser.pugx.org/laravel/lumen-framework/d/total.svg)](https://packagist.org/packages/laravel/lumen-framework)
[![Latest Stable Version](https://poser.pugx.org/laravel/lumen-framework/v/stable.svg)](https://packagist.org/packages/laravel/lumen-framework)
[![Latest Unstable Version](https://poser.pugx.org/laravel/lumen-framework/v/unstable.svg)](https://packagist.org/packages/laravel/lumen-framework)
[![License](https://poser.pugx.org/laravel/lumen-framework/license.svg)](https://packagist.org/packages/laravel/lumen-framework)

Docker Compose configuration to run PHP 7.2 with Nginx, PHP-FPM, MySQL 5.7 and Composer.

## Overview

his Docker Compose configuration lets you run easily PHP 7.1 with Nginx, PHP-FPM, PostgreSQL 10.1 and Composer.
It exposes 4 services:

* web (Nginx)
* php (PHP 7.2 with PHP-FPM)
* db (MySQL 5.7)
* composer

The PHP image comes with the most commonly used extensions.
Nginx default configuration and will serve your working directory.
Composer is run at boot time and will automatically install the vendors.

## Install prerequisites

For now the project has been tested on Linux only but should run fine on Docker for Windows and Docker for Mac.

You will need:

* [Docker CE](https://docs.docker.com/engine/installation/)
* [Docker Compose](https://docs.docker.com/compose/install)
* Git (optional)

## How to use it

### Starting Docker Compose

Checkout the repository or download the sources.

Simply run `docker-compose up` and you are done.

Nginx will be available on `localhost:80` and PostgreSQL on `localhost:5432`.

### Using Composer

`docker-compose run composer <cmd>`

Where `cmd` is any of the available composer command.

### Using PHP

You can execute any command on the `php` container as you would do on any docker-compose container:

`docker-compose exec php php -v`

## Change configuration

### Configuring PHP

To change PHP's configuration edit `.docker/conf/php/php.ini`.

You can add any .ini file in this directory, don't forget to map them by adding a new line in the php's `volume` section of the `docker-compose.yml` file.
