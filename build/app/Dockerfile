FROM php:7-fpm

# install wget and git in order to install php extensions from github. Added to install editor nano
RUN apt-get update && apt-get install -y wget git nano

#Install Composer globally
RUN curl -s -o /usr/local/bin/composer https://getcomposer.org/composer.phar && \
    chmod 0755 /usr/local/bin/composer

# Install gd
RUN apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libmcrypt-dev \
    libssl-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd \
    && docker-php-ext-install bcmath

# Install internationalization
RUN apt-get install -y\
    g++ \
    libicu-dev &&\
    docker-php-ext-install intl


# Install Laravel mysql
RUN apt-get install -y \
        mysql-client \
        zlib1g-dev

# Install zip extension
RUN docker-php-ext-install iconv mbstring \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install zip

# Install mongo
RUN pecl install mongodb \
    && docker-php-ext-enable mongodb

RUN apt-get update -y && \
    apt-get install -y mongodb

COPY /uploads.ini /usr/local/etc/php/conf.d/uploads.ini

WORKDIR /var/www/justiva
