FROM phpmyadmin/phpmyadmin:4.8.0
MAINTAINER WPLib Team <team@wplib.org>

ENV MYSQL_USER=wordpress
ENV MYSQL_PASSWORD=wordpress

COPY container.json /etc/container.json
COPY files /

EXPOSE 80
