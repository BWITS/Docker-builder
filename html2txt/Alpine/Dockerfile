# Convert html file to plain text file and run html2txt as local command
# suppose the html file `test.html` is at your current folder
#
# docker pull bwits/html2txt
# alias html2txt="docker run -ti --rm -v $(pwd):/app bwits/html2txt"
# html2txt /app/test.html /app/test.txt
# cat test.txt
FROM alpine:3.2

RUN apk --update add curl php php-curl php-openssl php-json php-phar php-dom && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
    rm /var/cache/apk/*

WORKDIR /var/www/html
ADD . /var/www/html

RUN composer install

ENTRYPOINT ["/usr/bin/php", "convert.php"]
