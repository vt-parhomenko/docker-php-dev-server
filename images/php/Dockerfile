FROM php:7.3-fpm

RUN apt-get update && apt-get install -y \
        curl \
        wget \
        git \
        libzip-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
        libwebp-dev \
        libxpm-dev

RUN docker-php-ext-install -j$(nproc) iconv mbstring mysqli pdo_mysql zip

RUN docker-php-ext-configure gd && docker-php-ext-install gd

RUN pecl install mcrypt-1.0.2 && docker-php-ext-enable mcrypt
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN yes | pecl install xdebug
RUN apt-get install cron -y && apt-get install nano -y

RUN pecl install redis && docker-php-ext-enable redis

RUN docker-php-ext-install pcntl && docker-php-ext-enable pcntl

ADD php.ini /usr/local/etc/php/conf.d/40-custom.ini
ADD xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini

WORKDIR /var/www/

USER www-data

CMD ["php-fpm"]
