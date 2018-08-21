## Laravel in Docker

With this article you’ll learn how to prepare a Docker image of a Laravel application, push it to the registry, and use Docker in Continuous Delivery.

## Requirements
- [GIT](https://git-scm.com/downloads).
- [Docker >= 17.12](https://www.docker.com/products/docker/).
## Installation
    
1. Install a new Laravel project or clone your project from github

        # git clone https://dev-andrew@bitbucket.org/justivaru/justiva.ru.git
        # cd myProject
        
2. Clone repository [Laravel in Docker](https://bitbucket.org/dev-andrew/docker-laravel/src/master/)

        # git clone https://dev-andrew@bitbucket.org/dev-andrew/docker-laravel.git docker
        # cd docker
3. Set your config in file docker-compose.yml

4. Change in 'environment' your database name, user and pass.
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
    
5. If you have changed the WORKDIR, you must change all docker files.

4. Start docker-compose.yml

        # dokcer-compose up -d
        
5. Kill all services

        # docker-compose kill
            

## Donations

> Help keeping the project development going donating a little. 
> Thanks in advance.

Donate directly via [Paypal](https://www.paypal.me/AndrewNdl)

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/AndrewNdl) 

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
