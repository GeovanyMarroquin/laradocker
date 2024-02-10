FROM ubuntu:jammy


# Set timezone:
RUN ln -snf /usr/share/zoneinfo/$CONTAINER_TIMEZONE /etc/localtime && echo $CONTAINER_TIMEZONE > /etc/timezone


RUN apt-get update && apt-get install -y locales wget tzdata && rm -rf /var/lib/apt/lists/* \
	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
ENV LANG en_US.utf8

RUN apt-get -y update

RUN apt install ca-certificates apt-transport-https software-properties-common lsb-release -y


# Instalando php 8.1
RUN add-apt-repository ppa:ondrej/php
RUN apt update -y
RUN apt install php8.2 -y
RUN apt-get install -y php8.2-cli php8.2-common php8.2-fpm php8.2-mysql php8.2-zip php8.2-gd php8.2-mbstring php8.2-curl php8.2-xml php8.2-bcmath

#Instalando composer
RUN apt install curl php-mbstring git unzip -y
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

#Instalando nodejs18
RUN curl -sL https://deb.nodesource.com/setup_18.x -o nodesource_setup.sh
RUN bash nodesource_setup.sh
RUN apt install nodejs -y

WORKDIR /var/www/html

EXPOSE 9090 9091 3306 5173