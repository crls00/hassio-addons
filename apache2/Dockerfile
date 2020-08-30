ARG BUILD_FROM
FROM $BUILD_FROM
ENV LANG C.UTF-8

# Create directory for apache2 to store PID file
RUN mkdir /run/apache2

RUN apk update && apk upgrade
RUN echo '@php72 http://dl-cdn.alpinelinux.org/alpine/v3.9/community' >> /etc/apk/repositories
RUN apk --no-cache add apache2 php7-apache2@php72 libxml2-dev apache2-utils apache2-mod-wsgi apache2-ssl
RUN apk --no-cache add php7@php72 php7-fpm@php72 php7-mysqli@php72 php7-opcache@php72 php7-gd@php72 php7-zlib@php72 php7-curl@php72 php7-phar@php72 php7-json@php72 php7-mbstring@php72 php7-mcrypt@php72 php7-zip@php72 php7-simplexml@php72 php7-tokenizer@php72 php7-session@php72
RUN apk --no-cache add icu-libs php7-fileinfo@php72 php7-openssl@php72 php7-intl@php72 php7-pdo_mysql@php72 php7-dom@php72 php7-xml@php72
RUN apk --no-cache add mariadb-client

# Copy data for add-on
COPY run.sh /
COPY index.html /
RUN chmod a+x /run.sh
RUN chmod a+x /index.html
CMD [ "/run.sh" ]
