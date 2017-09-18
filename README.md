# Docker

Solomon Hykes lightning talk  
https://www.youtube.com/watch?v=wW9CAH9nSLs


## Installation

* [Installation Mac](https://docs.docker.com/docker-for-mac/install/)  
* [Installation Windows](https://docs.docker.com/docker-for-windows/install/)  
* [Installation Linux](https://docs.docker.com/engine/installation/#desktop)  


## Docker cli

Kör ett kommando i en container

    docker run ubuntu /bin/echo "hello"

Gå in i en container

    docker run -i -t ubuntu /bin/bash

Kör php kod i en container

    docker run php:7.1-fpm php -r 'echo "Hello! My name is ".PHP_OS."\n";'

Kör ett lokalt php script

    mkdir project
    echo '<?php echo "Hello\! My name is ".PHP_OS."\n";' > ./project/hello.php
    docker run -v ${PWD}/project:/project php:7.1-fpm php /project/hello.php


## Laravel-applikation med docker-compose

    rm ./project/*
    git clone https://github.com/laravel/quickstart-basic project
    docker-compose up -d
    docker-compose exec php composer install
    docker-compose exec php php artisan key:generate
    docker-compose exec php php artisan migrate --seed


## NPM

    docker run -v ${PWD}/project:/project -w /project -p 3000:3000 node:6 /bin/bash -c "npm install && ./node_modules/.bin/gulp watch"

