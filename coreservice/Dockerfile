FROM php:fpm-alpine

# Set working directory
WORKDIR /var/www/html

# Install PHP Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN set -ex
RUN apk --no-cache add postgresql-dev
RUN docker-php-ext-install pdo pdo_pgsql

# Copy existing application directory
COPY . .

RUN chmod -R 777 storage bootstrap/cache storage/framework/views storage/framework/sessions storage/framework/cache storage/logs/laravel.log