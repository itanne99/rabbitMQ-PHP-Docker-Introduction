FROM php:7.4-apache
COPY --from=composer /usr/bin/composer /usr/bin/composer
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && sync && install-php-extensions amqp

COPY . /usr/src/myapp
WORKDIR /usr/src/myapp
CMD [ "composer" , "install"]
CMD ["tail" ,"-f", "/dev/null"]