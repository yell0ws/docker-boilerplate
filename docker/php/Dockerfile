FROM php:7.3.5-fpm

RUN apt-get update \
    && apt-get install -y \
        libssh-dev \
        zlib1g-dev \
    	libzip-dev \
        zip \
        git \
    && docker-php-ext-configure \
        zip — with-libzip

RUN curl -sS https://getcomposer.org/installer | \
    php -- --install-dir=/usr/bin/ --filename=composer

WORKDIR /var/www/app