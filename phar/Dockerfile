FROM php:7.1-alpine

ARG PHPSTAN_VERSION=0.8.4

RUN echo "memory_limit=-1" > $PHP_INI_DIR/conf.d/memory-limit.ini

RUN apk update --no-cache \
    && curl -LOs https://github.com/phpstan/phpstan/releases/download/${PHPSTAN_VERSION}/phpstan.phar \
    && chmod +x phpstan.phar \
    && mv phpstan.phar /usr/local/bin/phpstan \
    && rm -rf /var/cache/apk/* /var/tmp/* /tmp/*

VOLUME ["/app"]
WORKDIR /app

ENTRYPOINT ["/usr/local/bin/phpstan"]
