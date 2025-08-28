FROM php:8.1-fpm

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    libpq-dev \
    libzip-dev \
    zip \
 && docker-php-ext-install pdo pdo_pgsql zip

WORKDIR /var/www
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

RUN chown -R www-data:www-data /var/www || true

EXPOSE 9000
CMD ["php-fpm"]
