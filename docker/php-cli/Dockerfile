FROM php:8.2-cli

# Installing intl extension
RUN apt-get update && \
apt-get install -y \
    libzip-dev \
    zip && \
apt-get clean && \
rm -rf /var/lib/apt/lists/*

# Installing PHP extensions
RUN docker-php-ext-install zip

# Installing composer
COPY --from=composer:2.1 /usr/bin/composer /usr/local/bin/composer
ENV PATH="/root/.composer/vendor/bin:${PATH}"

# Setting working dir
WORKDIR /studies-doctrine