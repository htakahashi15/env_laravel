FROM php:7.4-fpm

#composerのインストール
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

#パッケージのインストール
RUN apt-get update && apt-get install -y \
  tzdata \
  zip \
  unzip \
  && pecl istall xdebug \
  && docker-php-ext-install pdo_mysql \
  && rm -rf /var/lib/apt/lists/*

ENV TZ=Asia/Tokyo
