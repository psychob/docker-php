FROM php:7.2-fpm-alpine
MAINTAINER Andrzej Budzanowski <kontakt@andrzej.budzanowski.pl>

RUN apk add --no-cache --virtual .phpize-deps $PHPIZE_DEPS                          &&  \
    apk add --no-cache postgresql-dev icu-dev zlib-dev gmp-dev zeromq-dev php7-zmq  &&  \
    pecl install -f xdebug zmq                                                      &&  \
    docker-php-ext-configure pgsql --with-pgsql                                     &&  \
    docker-php-ext-configure intl --enable-intl                                     &&  \
    docker-php-ext-install pdo pdo_pgsql pgsql intl zip bcmath gmp pcntl            &&  \
    docker-php-ext-enable bcmath gmp xdebug                                         &&  \
    echo "extension=zmq.so" > /usr/local/etc/php/conf.d/docker-php-ext-zmq.ini      &&  \
    apk del .phpize-deps

