FROM php:apache-stretch
MAINTAINER seike460

# setup
RUN buildDeps=" \
        default-libmysqlclient-dev \
        libbz2-dev \
        libmemcached-dev \
        libsasl2-dev \
    " \
    runtimeDeps=" \
        curl \
        git \
        libfreetype6-dev \
        libicu-dev \
        libjpeg-dev \
        libldap2-dev \
        libmemcachedutil2 \
        libpng-dev \
        libpq-dev \
        libxml2-dev \
    " \
    && apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y $buildDeps $runtimeDeps \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-configure ldap --with-libdir=lib/x86_64-linux-gnu/ \
    && docker-php-ext-install bcmath bz2 calendar iconv intl mbstring mysqli opcache pdo_mysql pdo_pgsql pgsql soap zip gd ldap exif \
    && pecl install xdebug redis \
    && docker-php-ext-enable xdebug.so redis.so \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && ln -s $(composer config --global home) /root/composer 
# clean
RUN apt-get purge -y --auto-remove $buildDeps \
    && rm -r /var/lib/apt/lists/*
# env & setup
ENV PATH $PATH:/root/composer/vendor/bin
RUN /bin/cp -f /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
RUN a2enmod rewrite
COPY template/php.ini /etc/php.ini
COPY template/apache2.conf /etc/apache2/apache2.conf

VOLUME ["/var/www/html"]
WORKDIR /var/www/html
