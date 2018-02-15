FROM php:7-fpm

# Git
RUN apt-get update && apt-get install -y git

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# xdebug
RUN pecl install xdebug && \
    docker-php-ext-enable xdebug

RUN usermod -u 1000 www-data
RUN chown -R www-data:www-data /var/www
WORKDIR /var/www/html/
USER www-data
