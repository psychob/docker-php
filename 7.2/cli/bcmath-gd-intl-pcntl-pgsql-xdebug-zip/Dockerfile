FROM rgblighthouse/php:7.2-cli
MAINTAINER Andrzej Budzanowski <kontakt@andrzej.budzanowski.pl>

RUN apk add --no-cache --virtual .phpize-deps $PHPIZE_DEPS                      &&  \
    apk add --no-cache postgresql-dev icu-dev zlib-dev gmp-dev libpng-dev       &&  \
    pecl install -f xdebug                                                      &&  \
    docker-php-ext-configure pgsql --with-pgsql                                 &&  \
    docker-php-ext-configure intl --enable-intl                                 &&  \
    docker-php-ext-install pdo pdo_pgsql pgsql intl zip bcmath gmp pcntl gd     &&  \
    docker-php-ext-enable bcmath gd gmp xdebug                                  &&  \
    apk del .phpize-deps

