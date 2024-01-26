# Use the official PHP 8.2 image with FPM support as the base image
FROM php:8.2-fpm

# Update package lists and install dependencies required for extensions
RUN apt-get update && apt-get install -y \
    libzip-dev \
    zlib1g-dev \
    libpng-dev

# Install the mysqli extension for MySQL database support in PHP
RUN docker-php-ext-install mysqli

# Use PECL to install and enable the Redis extension
RUN pecl install redis && docker-php-ext-enable redis

# Clean up unnecessary packages from the container
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

