
FROM php:7.1-fpm

MAINTAINER boer <boer0924@gmail.com>

LABEL Name=php-fpm Version=0.0.1

RUN apt-get update && apt-get install -y \
        # libmagickwand-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        libmemcached-dev \
        zlib1g-dev \
        # libpq-dev \
        --no-install-recommends \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd mcrypt gettext mysqli pdo_mysql \
    # && docker-php-ext-install -j$(nproc) gd mcrypt gettext mysqli pdo_mysql pgsql pdo_pgsql \
    # && pecl install yaf-3.0.4 \
    # && docker-php-ext-enable yaf \
    && pecl install memcached-3.0.3 \
    && docker-php-ext-enable memcached \
    # && pecl install imagick-3.4.3 \
    # && docker-php-ext-enable imagick \
    && pecl install swoole-1.9.8 \
    && docker-php-ext-enable swoole \
    && pecl install redis-3.1.2 \
    && docker-php-ext-enable redis \
    && apt-get autoremove \
    && apt-get clean \
    && apt-get autoclean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*