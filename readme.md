## Laravel in Docker

With this article you’ll learn how to prepare a Docker image of a Laravel application, push it to the registry, and use Docker in Continuous Delivery.

## Requirements
- [GIT](https://git-scm.com/downloads).
- [Docker >= 17.12](https://www.docker.com/products/docker/).
## Installation
    
1. Install a new Laravel project or clone your project from git

        # cd myProject
        
2. Clone repository [Laravel in Docker](https://bitbucket.org/dev-andrew/docker-laravel/src/master/)

        # git clone https://github.com/NdlAndrey/laravelDocker.git docker
        # cd docker
        
4. Set your config in file docker-compose.yml. Change in `environment` your database name, user and pass.
    - "DB_MYSQL_PORT=3306"
    - "DB_MYSQL_HOST=database"
    - "DB_MYSQL_DATABASE=justiva_mysql"
    - "DB_MYSQL_USERNAME=root"
    - "DB_MYSQL_PASSWORD=secret"
    >
    - "MYSQL_ROOT_PASSWORD=secret"
    - "MYSQL_DATABASE=justiva_mysql"
    >
    - "MONGO_INITDB_DATABASE=justiva"
    
4. If you have changed the WORKDIR, you must change all docker files.

5. Start docker-compose.yml

        # docker-compose up -d
        
6. Commands connect content and run php

        # docker-compose exec app bash // contect in ssh
  
7. Restore database for mysql and mongodb
 
        // run laravel artisan
        # docker-compose exec app php artisan migrate 
        
        // download dump
        # docker-compose exec app php artisan db:download
        
        // restore dump for mysql
        # docker-compose exec app php artisan db:restore mysql 
        
        // restore dump for monodb
        # docker-compose exec mongodb mongorestore --gzip --archive=database/dump/dump_mongo.gz --db justiva --drop
      
8. Kill all services

        # docker-compose kill
            

## Donations

> Help keeping the project development going donating a little. 
> Thanks in advance.

Donate directly via [Paypal](https://www.paypal.me/AndrewNdl)

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/AndrewNdl) 

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
