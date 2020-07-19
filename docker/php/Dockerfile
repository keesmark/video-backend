FROM php:7.4-fpm
COPY php.ini /usr/local/etc/php/

RUN apt-get update \
  && apt-get install -y libzip-dev \
  && docker-php-ext-install zip pdo_mysql \
  && curl -sL https://deb.nodesource.com/setup_12.x | bash - && apt-get install -y nodejs \
  && apt-get install -y \
  git \
  vim \
  curl \
  libpng-dev \
  libonig-dev \
  libxml2-dev \
  zip \
  unzip

RUN apt-get clean && rm -rf /var/lib/apt/lists/*

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer


WORKDIR /var/www/app

