FROM php:7.1-cli
MAINTAINER johan.vervloet@gmail.com

RUN apt-get update \
  && apt-get install -yq mysql-client libxml2-dev libmcrypt-dev libpng-dev git unzip zip \
  && docker-php-ext-install xml mcrypt gd pdo pdo_mysql mysqli mbstring 
RUN apt-get install -yq wget

RUN groupadd johanv \
  && useradd -g johanv -m johanv \
  && mkdir -p /var/www/html \
  && chown -R johanv:www-data /var/www \
  && chmod -R ug+rwX /var/www \
  && echo "[client] \n\
user=root \n\
password=blablablaroot \n\
host=db " > /home/johanv/.my.cnf \
  && cp /home/johanv/.my.cnf /root


