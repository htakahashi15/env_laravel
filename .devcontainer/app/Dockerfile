FROM php:7.4-fpm

#composerのインストール
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

#パッケージのインストール
RUN apt-get update && apt-get install -y \
  tzdata \
  zip \
  unzip \
  && pecl istall xdebug \
  && rm -rf /var/lib/apt/lists/* \
  && docker-php-ext-install pdo_pgsql

ENV TZ=Asia/Tokyo
