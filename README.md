# API/Webapp Docker Starter Base

This is a starter base to create and manage API/Webapp stack using docker

## dev CLI

Usage: `./dev <COMMAND>`

Available commands:
 - clean: stop services and remove containers. Equivalent to *`$ docker-compose stop && docker-compose rm -f`*
 - build: pass-thru to "build" (inside .docker) that build the images. Equivalent to *`$ ./docker/build <command>`*. `<command>`: all, api, angular and vue
 - destroy: stop services, remove containers and remove volumes. Equivalent to: *`$ docker-compose stop && docker-compose rm -f`* and *`$ docker volume rm $( $DOCKER volume ls -qf dangling=true)`*
 - artisan: pass-thru to "artisan" inside api container. Equivalent to: *`$ docker-compose run --rm -w "//var//www//html" api php artisan <command>`*
 - composer
 - test
 - node
 - vue
 - angular
 - npm
 - gulp
 - webpack 
        

## Images
### api
Contains: PHP 7.2, ngnix (latest), composer (latest)

### mysql
- MySQL 5.7
### node-angular-cli
- Nodejs 8.9.4
- git(latest)
- yarn (latest)
### node-vue-cli
- Nodejs 8.9.4
- git (latest)
- yarn (latest)
- webpack (v3.10.0)
- vue-cli (v2.9.3)


Notes:
- If Windows use Git CMD instead Git Bash as described [here](http://willi.am/blog/2016/08/08/docker-for-windows-interactive-sessions-in-mintty-git-bash/)