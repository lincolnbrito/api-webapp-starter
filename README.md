# [WIP] API/Webapp Docker Starter Base

This is a starter base to create and manage API/Webapp stack using docker

## Directories
<pre>
/
|
|_.docker
|    |__api
|    |
|    |__mysql
|    |    |__ conf.d
|    |    |__ logs
|    |
|    |__node-angular-cli
|    |    |__ Dockerfile
|    |
|    |__node-vue-cli
|    |    |__ Dockerfile
|    |
|    |__volume-data
|    |
|    |_ .env-example
|    |_ .gitignore
|    |_ build
|    |_ docker-compose.yml
|
|__api - API code
|
|__webapp
|  |__angular - angular apps
|  |__vue - vue apps
|
|_ .gitignore
|
|- dev - Script
|
|_ README.md - This file
</pre> 

## dev CLI
A utilitary script to help with workflow.

Usage:
```
./dev <COMMAND>
```

Available commands:

|  Command | Description    |
|---|---|
| **up** | start services. `up <service>` to start a single service |
|**down**| stop services. `down <service>` to stop a single service|
|**clean**| stop services and remove containers|
|**build**| pass-thru to "build" script (inside .docker) to build images. |
|**destroy**| stop services, remove containers and remove volumes. |
|**bash**| run a bash session inside api container. |
|**artisan**| run "artisan" inside api container. |
|**composer**| run "composer" inside api container. |
|**test**| run "phpunit" tests inside api container|
|**node**| run "node" inside node-vue-cli container. |
|**vue**| run "vue-cli" inside node-vue-cli container. |
|**angular**| run "ng-cli" inside node-angular-cli container. |
|**npm**| run "npm" inside node-vue-cli|
|**gulp**| run "gulp" inside node-vue-cli|
|**webpack**| run "webáck" inside node-vue-cli|
        

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

## Enviroment Variables
### Api
- `COMPOSER_CACHE_DIR=/f/WWW/.composer_cache`
- `WWWUSER=1337`
- `API_DIR=../api`
- `API_ENV=local`
- `API_PORT=80`
### MySQL
- `MYSQL_PORT=3306`
- `MYSQL_ROOT_PASSWORD=secret`
- `MYSQL_DATABASE=api_webapp_db`
- `MYSQL_USER=api_webapp_user`
- `MYSQL_PASSWORD=secret`
### Webapps
- `WEBAPP_VUE_DIR=..\webapp\vue`
- `WEBAPP_VUE_PORT=8080`
- `WEBAPP_ANGULAR_DIR=../webapp/angular`
- `WEBAPP_ANGULAR_PORT=4200`
### Shared Data
- `VOLUME_DATA_PATH=./volume-data`

## Notes:
- If using Windows prefer to use Git CMD instead Git Bash as described [here](http://willi.am/blog/2016/08/08/docker-for-windows-interactive-sessions-in-mintty-git-bash/)

- Line-ending issue with entrypoint.sh when build image with Windows: 
    - https://stackoverflow.com/questions/38905135/why-wont-my-docker-entrypoint-sh-execute
    - http://willi.am/blog/2016/08/11/docker-for-windows-dealing-with-windows-line-endings/