# Convert html file to plain text file and run html2txt as local command
# suppose the html file `test.html` is at your current folder
#
# docker pull bwits/html2txt
# alias html2txt="docker run -ti --rm -v $(pwd):/app bwits/html2txt"
# html2txt /app/test.html /app/test.txt
# cat test.txt
FROM composer/composer

WORKDIR /var/www/html
ADD . /var/www/html

RUN composer install
ENTRYPOINT ["/usr/local/bin/php", "convert.php"]
