FROM php:5.6-fpm

RUN apt-get update \
    && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        libxml2-dev \
        libsasl2-dev \
        libbz2-dev \
        build-essential \
        wget \
        git \
        gettext

EXPOSE 9000

CMD ["php", "-a"]
