FROM php:7.1-apache

RUN mkdir /www
COPY astro-maki /www/
RUN chmod -R 777 /www/storage
COPY conf/000-default.conf /etc/apache2/sites-available/000-default.conf
COPY conf/php.ini /usr/local/etc/php/conf.d/php.ini

RUN a2enmod rewrite
RUN apt update
RUN apt install -y vim
RUN apt install -y libpng-dev libfreetype6-dev
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/
RUN docker-php-ext-install gd
RUN docker-php-ext-install mbstring

COPY swiss /swiss
RUN chmod +x /swiss/swetest2

