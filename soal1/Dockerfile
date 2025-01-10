FROM php:8-apache AS installer

WORKDIR /var/www/html

RUN apt update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer


RUN docker-php-ext-install pdo_mysql mbstring gd


COPY . .


RUN composer install

COPY apache/000-default.conf /etc/apache2/sites-enabled/

RUN chown -R www-data:www-data storage

EXPOSE 80
