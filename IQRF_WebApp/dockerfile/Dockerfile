#IQRF Daemon webApp Image for the UP board
FROM php:7.0-apache
MAINTAINER Vojtěch Novák "jotio@outlook.cz"
RUN	apt-get update \
	&& apt-get install -y git \
	&& apt-get install --yes zip unzip php-pclzip \
	&& cd /usr/ \
	&& curl -s http://getcomposer.org/installer | php \
	&& mv ./composer.phar /usr/local/bin/composer \
	&& git clone https://github.com/iqrfsdk/iqrf-daemon-webapp.git \
	&& cd /usr/iqrf-daemon-webapp/ \
	&& composer install \
	&& chmod 777 temp \
	&& chmod 777 log \
	&& composer create-project iqrfsdk/iqrf-daemon-webapp \
	&& apt-get clean \
	&& rm -rf /var/lib/apt/lists/*

EXPOSE 8000 80

#CMD [ "php", "/usr/iqrf-daemon-webapp/www/index.php" ]
ENTRYPOINT  php -S localhost:8000 -t /usr/iqrf-daemon-webapp/www/







#FROM resin/up-board-debian:latest



# install daemon
#RUN	apt-get update \
#	&& apt-get install -y git \
#	&& apt-get install -y php5 \
#	&& cd /usr/ \
#	&& curl -s http://getcomposer.org/installer | php \
#	&& mv ./composer.phar /usr/local/bin/composer \
#	&& git clone https://github.com/iqrfsdk/iqrf-daemon-webapp.git \
#	&& cd /usr/iqrf-daemon-webapp/ \
#	&& composer install \
#	&& chmod 777 temp \
#	&& chmod 777 log \
#	&& composer create-project iqrfsdk/iqrf-daemon-webapp \
#	&& apt-get clean \
#	&& rm -rf /var/lib/apt/lists/*
#EXPOSE 8000
#ENTRYPOINT  php -S localhost:8000 -t /usr/iqrf-daemon-webapp/www/
