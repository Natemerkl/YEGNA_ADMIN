FROM php:8.2-fpm

# Set working directory
WORKDIR /var/www

# Copy existing application directory contents
COPY . .

# Install dependencies
RUN apt-get update && apt-get install -y libzip-dev \
    && docker-php-ext-install zip \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && composer install --no-dev

# Expose port 9000
EXPOSE 9000

# Start the PHP FastCGI Process Manager
CMD ["php-fpm"]
