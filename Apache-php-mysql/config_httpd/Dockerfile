From php:7-apache

ADD ["vh05_curriculo.conf","/etc/apache2/sites-available/000-default.conf"]

RUN apt-get update && apt-get install -y libzip-dev zip

RUN  docker-php-ext-configure zip --with-libzip && docker-php-ext-install mbstring pdo pdo_mysql zip exif  && a2enmod rewrite negotiation && docker-php-ext-install opcache

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN service apache2 restart

EXPOSE 80