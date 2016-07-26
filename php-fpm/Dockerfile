FROM php:7.0-fpm
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        mysql-client \
        iproute2 \
        net-tools \
        libmemcached-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install -j$(nproc) opcache \
    && docker-php-ext-install -j$(nproc) mysqli \
    && docker-php-ext-install -j$(nproc) pdo_mysql \
    && docker-php-ext-install -j$(nproc) mbstring
    # && docker-php-ext-install /-j$(nproc) bz2 

# RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
# 	&& php composer-setup.php \
# 	&& php -r "unlink('composer-setup.php');" \
# 	&& composer global require drush/drush:8.1.0 global require drush/drush:8.1.0

RUN apt-get -y update && apt-get -y install git	

WORKDIR "/var/www/dai-usaid-docker-webstarter"