FROM node:6.10.3

RUN mkdir -p /srv/www/borisbar/src/frontend
WORKDIR /srv/www/borisbar/src/frontend

RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/* \
    && npm install -g bower polymer-cli@1.1.0

RUN echo '{ "allow_root": true }' > /root/.bowerrc
ENV DOCKER_FIX=' '
EXPOSE 8080
