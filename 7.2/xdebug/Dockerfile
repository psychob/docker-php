FROM php:7.2-fpm-alpine
MAINTAINER Andrzej Budzanowski <kontakt@andrzej.budzanowski.pl>

RUN apk add --no-cache --virtual .phpize-deps $PHPIZE_DEPS      &&  \
    pecl install xdebug                                         &&  \
    docker-php-ext-enable xdebug                                &&  \
    apk del .phpize-deps
