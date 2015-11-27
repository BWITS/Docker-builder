FROM composer/composer

WORKDIR /var/www/html
ADD . /var/www/html

RUN composer install

ENTRYPOINT ["/usr/local/bin/php", "convert.php"]
