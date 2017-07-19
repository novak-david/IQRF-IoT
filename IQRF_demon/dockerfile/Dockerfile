
#IQRF Daemon Image for the UP board

FROM resin/up-board-debian:latest
MAINTAINER Rostislav Spinar "rostislav.spinar@microrisc.com"

# update repos
RUN echo "deb http://repos.iqrfsdk.org/debian jessie testing" | sudo tee -a /etc/apt/sources.list.d/iqrf-daemon.list \
    && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys F973CFCE6B3BE25C

# install daemon
RUN	apt-get update \
	&& apt-get install -y iqrf-daemon \
	&& apt-get install -y git \
	&& apt-get install -y php5 \
	&& cd /usr/ \
	&& curl -s http://getcomposer.org/installer | php \
	&& mv ./composer.phar /usr/local/bin/composer \
	&& git clone https://github.com/iqrfsdk/iqrf-daemon-webapp.git \
	&& cd /usr/iqrf-daemon-webapp/ \
	&& composer install \
	&& chmod 777 temp \
	&& chmod 777 log \
	&& composer create-project iqrfsdk/iqrf-daemon-webapp \
	#&& php -S localhost:8000 -t www/ \
	&& apt-get clean \
	&& rm -rf /var/lib/apt/lists/*
EXPOSE 8000
# 
ENTRYPOINT  php -S localhost:8000 -t www/ && /usr/bin/iqrf_startup /etc/iqrf-daemon/config.json
