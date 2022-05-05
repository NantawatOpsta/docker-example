FROM php:7.4-fpm

#RUN apt update
#RUN apt install -y vim

COPY . /usr/src/myapp
WORKDIR /usr/src/myapp
CMD [ "php", "-S", "0.0.0.0:8000", "info.php" ]
