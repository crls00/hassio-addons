ARG BUILD_FROM
FROM $BUILD_FROM
ENV LANG C.UTF-8

# Create directory for apache2 to store PID file
RUN mkdir /run/apache2

RUN apk update && apk upgrade
#RUN echo ' http://dl-cdn.alpinelinux.org/alpine/v3.9/community' >> /etc/apk/repositories
RUN apk --no-cache add apache2 php7-apache2 libxml2-dev apache2-utils apache2-mod-wsgi apache2-ssl
RUN apk --no-cache add php7 php7-fpm php7-mysqli php7-opcache php7-gd php7-zlib php7-curl php7-phar php7-json php7-mbstring php7-mcrypt php7-zip php7-simplexml php7-tokenizer php7-session
RUN apk --no-cache add icu-libs php7-fileinfo php7-openssl php7-intl php7-pdo_mysql php7-dom php7-xml
RUN apk --no-cache add mariadb-client

# Copy data for add-on
COPY run.sh /
COPY index.html /
RUN chmod a+x /run.sh
RUN chmod a+x /index.html
CMD [ "/run.sh" ]
