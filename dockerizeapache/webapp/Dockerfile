FROM php:7.4-apache

# Arguments defined in docker-compose.yml
ARG user
ARG uid

# Install system dependencies

# Clear cache
#RUN apt-get clean && rm -rf /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y \
        libicu-dev \
    && apt-get install -y \
        libonig-dev \
    && docker-php-ext-install \
        intl \
    && docker-php-ext-enable \
        intl
# Install PHP extensions
RUN docker-php-ext-install mysqli pdo pdo_mysql mbstring 

WORKDIR /var/www/html

RUN a2enmod rewrite

RUN service apache2 restart