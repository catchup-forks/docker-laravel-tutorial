FROM php:7.1-fpm

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        libssl-dev \
        git

RUN docker-php-ext-install iconv mcrypt mbstring pdo pdo_mysql zip

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

