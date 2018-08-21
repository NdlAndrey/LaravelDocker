FROM php:7-fpm

# install wget and unzip in order to install php extensions from github
RUN apt-get update && apt-get install -y wget

RUN apt-get update
RUN apt-get install -y autoconf pkg-config libssl-dev
RUN docker-php-ext-install bcmath
# RUN echo "extension=mongodb.so" >> /usr/local/etc/php/conf.d/mongodb.ini

# Install Laravel dependencies
RUN apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        mysql-client \
        zlib1g-dev

RUN docker-php-ext-install iconv mbstring \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install zip \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd

RUN pecl install mongodb \
    && docker-php-ext-enable mongodb

COPY /uploads.ini /usr/local/etc/php/conf.d/uploads.ini

WORKDIR /var/www/justiva
