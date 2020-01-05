FROM php:7.4-fpm

RUN apt-get update && apt-get install -y libpq-dev libpng-dev libcurl3-dev \
        libzip-dev \
        zip \
        wget \
    && docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql \
    && docker-php-ext-install pdo pdo_pgsql gd \
    && docker-php-ext-install curl

WORKDIR /var/www