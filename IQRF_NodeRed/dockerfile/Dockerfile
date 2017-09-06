# Nodered Image for the IQRF IoT Starter Kit run on UP board

FROM nodered/node-red-docker:latest 
MAINTAINER Vojtěch Novák "jotio@outlook.com"

# install ext.
RUN cd /data \
  && rm settings.js \
  && apt-get update \
  && apt-get install -y git \	
  && git clone https://github.com/JoTioTech/JoTio_NodeRed.git \
  && cd JoTio_NodeRed \
  && cp flows.json /data \
  && cp settings.js /data \
  && chown -R node-red:node-red /data \
  && npm i node-red/node-red-dashboard 
#	&& npm i node-red-node-watson \
#	&& npm i node-red-contrib-scx-ibmiotapp 
# && rm flows.json \
EXPOSE 1880 9001 
