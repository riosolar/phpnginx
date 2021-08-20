# Main image
FROM php:7.4-fpm

# Update and install modules for php and other
RUN apt-get update && apt-get install -y \      
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && apt-get install -y wget zip unzip git \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd pdo mysqli pdo_mysql \
    && docker-php-ext-enable mysqli

# Workdir for php
WORKDIR /var/www

# Run container
CMD ["php-fpm"]
