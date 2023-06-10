FROM php:8.2-fpm

RUN apt-get update && apt-get install -y zlib1g-dev g++ git libicu-dev zip libzip-dev zip \
    && docker-php-ext-install intl opcache pdo pdo_mysql \
    && pecl install apcu xdebug \
    && docker-php-ext-enable apcu xdebug \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip

# INSTALL COMPOSER
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# INSTALL SYMFONY
RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony5/bin/symfony /usr/local/bin/symfony

# WORK DIR
WORKDIR /var/www/project