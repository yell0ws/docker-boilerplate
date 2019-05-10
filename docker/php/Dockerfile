FROM php:7.3.5-fpm

RUN apt-get update \
    && apt-get install -y \
        librabbitmq-dev \
        libssh-dev \
	zlib1g-dev \
    	libzip-dev \
	zip \
	git \
    && docker-php-ext-install \
        bcmath \
        sockets \
    && pecl install \
	amqp \
	xdebug \
    && docker-php-ext-configure \
	zip — with-libzip \
    && docker-php-ext-enable \ 
	amqp \
	xdebug

RUN curl -sS https://getcomposer.org/installer | \
    php -- --install-dir=/usr/bin/ --filename=composer

WORKDIR /var/www/app