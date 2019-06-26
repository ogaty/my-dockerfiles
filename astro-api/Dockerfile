FROM php:7.2-apache

RUN mkdir /www
COPY src /www/
COPY conf/000-default.conf /etc/apache2/sites-available/000-default.conf
COPY conf/php.ini /usr/local/etc/php/conf.d/php.ini

RUN a2enmod rewrite
RUN apt update
RUN apt install -y vim

COPY swiss /swiss
RUN chmod +x /swiss/sweph

