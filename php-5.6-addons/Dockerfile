FROM php:5.6-apache
RUN a2enmod rewrite
RUN apt-get update \
  && apt-get install -y ghostscript pdftohtml imagemagick libmemcached11 libmemcachedutil2 build-essential libmemcached-dev libz-dev libmagickwand-dev --no-install-recommends \
  && pecl install memcache \
  && pecl install imagick \
  && docker-php-ext-install mysql pdo_mysql \
  && docker-php-ext-enable imagick \
  && docker-php-ext-enable opcache \
  && docker-php-ext-enable memcache \
  && apt-get remove -y build-essential libmemcached-dev libz-dev \
  && apt-get autoremove -y \
  && apt-get clean \
  && rm -rf /tmp/pear \
  && rm -rf /var/lib/apt/lists/*
