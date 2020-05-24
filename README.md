# WordPress Docker Debugging
Deploys WordPress on Docker with XDebug configured

## Why?

For a Wordpress developer sometimes it's quite useful to debug some code on a plain vanila web. This set of Docker configuration files will spin a working instance in no time which can be easily debugged using PhpStorm

## What's inside

`docker-compose.yml` provides three services:

1. The latest WordPress running on Apache.
    - Use the `wordpress\Dockerfile` to further customize the container. Here we're using XDebug 2.9.5.
  - You can further customize the Prestashop deployement by tweaking the `Environment` keys, check the [https://hub.docker.com/_/wordpress/](Docker Hub Wordpress container) for further reference. 
2. A standalone MariaDB instance that can be further inspected by..
3. ... a PhpMyAdmin instance


 ### How to run
 
 - `docker-compose up`
 - navigate to `http://wordpress.local` (remember to configure your hosts accordingly)
 - inspect the database in http://localhost:8080
 - `docker-compose down --volumes --remove-orphans` once you're done. Remember to delete the `.\fs` folder or you'll get an error when redeploying the containers.
