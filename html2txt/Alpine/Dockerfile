FROM alpine:3.2

RUN apk --update add curl php php-curl php-openssl php-json php-phar php-dom && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
    rm /var/cache/apk/*

WORKDIR /var/www/html
ADD . /var/www/html

RUN composer install

ENTRYPOINT ["/usr/bin/php", "convert.php"]
