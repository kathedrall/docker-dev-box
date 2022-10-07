FROM php:7.4-fpm-alpine

ARG DEBIAN_FRONTEND=noninteractive

RUN docker-php-ext-install mysqli

RUN apk add --no-cache $PHPIZE_DEPS \
    && pecl install xdebug-3.1.0 \
    && docker-php-ext-enable xdebug \
    && docker-php-ext-install pdo_mysql

RUN apk add --no-cache composer

VOLUME "/src"

EXPOSE 9000