# WP-Docker - WordPress Docker Compose

Easy WordPress development with Docker and Docker Compose.

With this project you can quickly run the following:

- [WordPress and WP CLI](https://hub.docker.com/_/wordpress/)
- [phpMyAdmin](https://hub.docker.com/_/phpmyadmin/)
- [MySQL](https://hub.docker.com/_/mysql/)

Contents:

- [Requirements](#requirements)
- [Configuration](#configuration)
- [Installation](#installation)
- [Usage](#usage)

## Requirements

Make sure you have the latest versions of **[Docker](https://docs.docker.com/engine/install/)** and **[Docker Compose](https://docs.docker.com/compose/install/)** installed on your machine.

Clone this repository or copy the files from this repository into a new folder. In the **docker-compose.yml** file you may change the database from MySQL to MariaDB.

Make sure to [add your user to the `docker` group](https://docs.docker.com/install/linux/linux-postinstall/#manage-docker-as-a-non-root-user) when using Linux.

## Configuration 
Edit the `.env` file to change  MySQL root password and WordPress database name.
```
# Database Configuration
DB_ROOT_PASSWORD='Root_password'
DB_NAME='Namedatabase'
DB_USER='uername'
DB_PASSWORD='password'

```
## Installation

Open a terminal and `cd` to the folder in which `docker-compose.yml` is saved and run:

```
docker-compose up
```

This creates two new folders next to your `docker-compose.yml` file.

* `wp-content` – the location of your WordPress application

The containers are now built and running. You should be able to access the WordPress installation with IP `http://127.0.0.1:8080` and You can also visit `http://127.0.0.1:8081` to access phpMyAdmin after starting the containers.The default username is `root`, and the password is the same as supplied in the `.env` file.
For convenience you may add a new entry into your hosts file.

## Usage

### Starting containers

You can start the containers with the `up` command in daemon mode (by adding `-d` as an argument) or by using the `start` command:

```
docker-compose start
```

### Stopping containers

```
docker-compose stop
```

### Removing containers

To stop and remove all the containers use the`down` command:

```
docker-compose down
```
