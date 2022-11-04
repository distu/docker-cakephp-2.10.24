FROM php:7.4.20-apache

# php の拡張機能に必要なライブラリをインストール
RUN apt-get update && \
    apt-get install libicu-dev libzip-dev libpng-dev libpq-dev unzip sqlite3 -y
RUN docker-php-ext-install intl pgsql pdo_pgsql zip gd

# Apache の設定
RUN a2enmod rewrite
COPY ./000-default.conf /etc/apache2/sites-enabled/000-default.conf

# composer version 1 のインストール
RUN curl -sS https://getcomposer.org/composer-1.phar -o composer.phar && \
    mv composer.phar /usr/local/bin/composer && \
    chmod a+x /usr/local/bin/composer
