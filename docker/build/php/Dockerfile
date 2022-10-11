FROM php:7.4-fpm-alpine

ARG DEBIAN_FRONTEND=noninteractive

RUN docker-php-ext-install mysqli \
    && docker-php-ext-install bcmath \  
    && docker-php-ext-install opcache \
    && docker-php-ext-install pdo_mysql


RUN apk add --no-cache $PHPIZE_DEPS \
    && pecl install xdebug-3.1.0 \
    && pecl install ds \
    && pecl install apcu \
    && pecl install redis \
    && docker-php-ext-enable xdebug \
    && docker-php-ext-enable redis \
    && docker-php-ext-enable apcu \
    && docker-php-ext-enable ds

RUN apk add --no-cache composer

VOLUME "/src"

EXPOSE 9000