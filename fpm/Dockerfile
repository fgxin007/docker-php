FROM php:7.2-fpm
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libssl-dev \
        libcurl4-gnutls-dev \
        libxml2-dev \
    && docker-php-ext-install pdo_mysql mysqli mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install -j$(nproc) bcmath \
    && docker-php-ext-install -j$(nproc) soap \
    && docker-php-ext-install -j$(nproc) zip \
    && pecl install mongodb \
    && docker-php-ext-enable mongodb \
    && pecl install solr \
    && docker-php-ext-enable solr \
    && pecl install swoole \
    && docker-php-ext-enable swoole \
    && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime