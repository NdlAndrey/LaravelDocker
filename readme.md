## Laravel in Docker

With this article you’ll learn how to prepare a Docker image of a Laravel application, push it to the registry, and use Docker in Continuous Delivery.

## Requirements
- [GIT](https://git-scm.com/downloads).
- [Docker >= 17.12](https://www.docker.com/products/docker/).
## Installation
    
1. Create/download Laravel project, go to inside project ```cd project```
        
2. Clone repository [Laravel in Docker](https://bitbucket.org/dev-andrew/docker-laravel/src/master/) inside project and go to folder ```docker``` (your can change name folder)
    
        git clone https://github.com/NdlAndrey/laravelDocker.git docker
        cd docker
        
3. Set username, password and database for mysql ```docker-compose.yml```

        mysql:
            environment:
                - "MYSQL_DATABASE=db_name"
                - "MYSQL_USER=homestead"
                - "MYSQL_PASSWORD=secret"
                - "MYSQL_ROOT_PASSWORD=root_secret"
                
4. For ```install``` or ```up``` docker use command 
    
        dokcer-compose up -d
        
    from docker folder (default ```docker```)

## Helpers commands
> All docker command execute from docker folder (default ```docker```)

#### Enter the app container, to execute commands like (Artisan, Composer, Gulp, …) 
        
        docker-compose exec app bash
        
#### List current running Containers
    
    docker ps
    
#### Close all running Containers

    docker-compose stop

To stop single container do:

    docker-compose stop {container-name}
    
#### Delete all existing Containers

    docker-compose down
    
#### Kill all services

    docker-compose kill
        
## Donations

> Help keeping the project development going donating a little. 
> Thanks in advance.

Donate directly via [Paypal](https://www.paypal.me/AndrewNdl)

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/AndrewNdl) 

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
