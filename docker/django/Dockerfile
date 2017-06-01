FROM python:3.5.1-alpine

RUN apk add --no-cache --virtual .django-deps\
            gcc \
            postgresql-dev \
            musl-dev \
    && apk add --no-cache \
            postgresql-client \
            jpeg-dev \
            zlib-dev

ENV LIBRARY_PATH=/lib:/usr/lib

RUN mkdir -p /srv/www/borisbar/src/backend \
    && mkdir -p /srv/www/borisbar/src/media \
    && mkdir -p /srv/www/borisbar/src/static
WORKDIR /srv/www/borisbar/src/backend

COPY requirements.txt /srv/www/borisbar/src/backend/
RUN pip3 install --no-cache-dir -r requirements.txt

RUN apk del .django-deps \
	&& rm -rf ~/.cache

EXPOSE 8000
