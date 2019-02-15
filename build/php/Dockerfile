FROM php:7.1-fpm-stretch

RUN apt-get update && apt-get install -y zip unzip libmemcached-dev zlib1g-dev git vim \
    && docker-php-ext-install pdo_mysql \
    && pecl install memcached-3.1.2 \
    && pecl install redis-4.0.1 \
    && pecl install xdebug-2.6.1 \
    && pecl install swoole \
    && docker-php-ext-enable memcached redis xdebug swoole

# Install php composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer