#IQRF Daemon webApp Image for the UP board
FROM resin/up-board-debian:latest

MAINTAINER Vojtěch Novák "jotio@outlook.cz"
RUN	apt-get update \
	&& apt-get install -y git \
	#&& sudo apt-get install python3 \
	&& apt-get install --yes zip unzip php-pclzip \
	&& git clone https://github.com/iqrfsdk/iqrf-daemon-webapp.git \
	&& cd /usr/iqrf-daemon-webapp/install \
	&& chmod 777 install.sh \
	#&& python3 install.py -d debian -v 9 \
	&& apt-get clean \
	&& rm -rf /var/lib/apt/lists/*

EXPOSE 8000 80

#CMD [ "php", "/usr/iqrf-daemon-webapp/www/index.php" ]
#ENTRYPOINT  php -S localhost:8000 -t /usr/iqrf-daemon-webapp/www/
ENTRYPOINT /usr/iqrf-daemon-webapp/install/install.sh ; /bin/bash
