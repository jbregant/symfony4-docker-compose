FROM alpine:3.8

RUN apk add --update \
    openrc \
    file \
    re2c \
    autoconf \
    make \
    zlib \
    zlib-dev \
    g++ \
    php7-fpm \
    php7-apcu \
    php7-ctype \
    php7-curl \
    php7-dev \
    php7-dom \
    php7-gd \
    php7-iconv \
    php7-imagick \
    php7-json \
    php7-intl \
    php7-mcrypt \
    php7-fileinfo\
    php7-mbstring \
    php7-opcache \
    php7-openssl \
    php7-pear \
    php7-pdo \
    php7-pdo_mysql \
    php7-pdo_pgsql \
    php7-pgsql \
    php7-mysqli \
    php7-xml \
    php7-zlib \
    php7-phar \
    php7-tokenizer \
    php7-session \
    php7-simplexml \
    php7-xdebug \
    php7-zip \
    php7-soap \
    nodejs \
    yarn \
    npm \
    make \
    curl \ 
    git \
    mc

RUN rm -rf /var/cache/apk/* && rm -rf /tmp/* && \
    curl --insecure https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer

RUN wget https://pecl.php.net/get/redis-4.2.0.tgz && pecl install redis-4.2.0.tgz

ADD symfony.ini /etc/php7/conf.d/
ADD xdebug.ini  /etc/php7/conf.d/
ADD redis.ini  /etc/php7/conf.d/
ADD symfony.ini /etc/php7/cli/conf.d/

ADD symfony.pool.conf /etc/php7/php-fpm.d/

CMD ["php-fpm7", "-F"]

WORKDIR /var/www/symfony
EXPOSE 9001
