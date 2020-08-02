FROM php:7.4-apache

RUN set -x \
    && apt-get -y update \
    && apt-get install -y curl zlib1g-dev unzip git libpng-dev \
      npm

RUN set -x \
    && docker-php-ext-configure pdo_mysql --with-pdo-mysql=mysqlnd --with-libdir=lib/x86_64-linux-gnu/ \
    && docker-php-ext-configure mysqli --with-mysqli=mysqlnd --with-libdir=lib/x86_64-linux-gnu/ \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install gd

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf

RUN a2enmod rewrite
