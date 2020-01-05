FROM php:7.4-fpm

RUN apt-get update && apt-get install -y libpq-dev libpng-dev libcurl3-dev \
        libzip-dev \
        zip \
        wget \
    && docker-php-ext-configure zip --with-libzip \
    && docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql \
    && docker-php-ext-install pdo pdo_pgsql gd \
    && docker-php-ext-install curl \
        zip

WORKDIR /var/www

#FROM php:7.2-fpm
#
#RUN apt-get update && apt-get install -y libpq-dev libpng-dev zlib1g-dev libmcrypt-dev \
#        libzip-dev \
#        zip \
#        wget \
#        libfreetype6-dev \
#        libjpeg62-turbo-dev \
#        libmcrypt-dev \
#        libpng-dev \
#    && docker-php-ext-configure zip --with-libzip \
#    && docker-php-ext-install mysqli pdo pdo_mysql \
#    && pecl install \
#    && pecl install mcrypt-1.0.1 \
#    && docker-php-ext-enable mcrypt \
#    && docker-php-ext-enable pdo_mysql \
#    && docker-php-ext-install gd \
#    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
#    && docker-php-ext-install -j$(nproc) gd
#
#WORKDIR /var/www
#
#
##FROM php:7.2-fpm-stretch
##
##
##RUN apt-get update && apt-get install -y git zlib1g-dev libmcrypt-dev \
##        libzip-dev \
##        zip \
##        wget \
##        libfreetype6-dev \
##        libjpeg62-turbo-dev \
##        libmcrypt-dev \
##        libpng-dev \
##    && docker-php-ext-configure zip --with-libzip \
##    && docker-php-ext-install mysqli pdo pdo_mysql \
##        zip \
##    && pecl install \
##    && pecl install mcrypt-1.0.1 \
##    && docker-php-ext-enable mcrypt \
##    && docker-php-ext-enable pdo_mysql \
##    && docker-php-ext-install gd \
##    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
##    && docker-php-ext-install -j$(nproc) gd
##
##
##RUN useradd -ms /bin/bash docker && adduser docker sudo
### Users in the sudoers group can sudo as root without password.
##RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
##
##
##
### install Composer
##COPY env/php-fpm/scripts/install-composer /usr/local/bin/install-composer
##RUN chmod +x /usr/local/bin/install-composer && install-composer
##
##
##
##WORKDIR /var/www
##
##COPY . .
##
###RUN usermod -u 1000 www-data
##
##RUN composer install --no-plugins --no-scripts
##
##
##RUN chown docker:docker /var/www
##
##RUN chmod -R 0777  /var/www/storage/
##
##RUN chmod -R 0777  /var/www/bootstrap/
##
##USER docker