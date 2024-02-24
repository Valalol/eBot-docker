FROM php:7.4-fpm-bookworm

RUN apt-get update && apt-get install -y --force-yes git && apt-get clean

WORKDIR /app

RUN docker-php-ext-install mysqli pdo pdo_mysql && docker-php-ext-enable pdo_mysql

RUN echo 'date.timezone = Europe/Paris' >> /usr/local/etc/php/conf.d/timezone.ini

COPY setup.sh .

RUN chmod +x setup.sh

CMD ["./setup.sh"]
