FROM php:8-fpm-alpine
  RUN apk add mc \ 
  && apk add composer \
  && apk add nodejs \
  && apk add npm \
  && apk add git \
  && set -ex \
  && apk --no-cache add \
    postgresql-dev \
  && docker-php-ext-install \ 
    pdo \
    pdo_mysql \
    pdo_pgsql 
#  ENV DEPENDENSIES="git libzip mysql-client curl libmcrypt libmcrypt-dev openssh-client icu-dev libxml2-dev libxslt-dev espeak "
#  ENV DEPENDENSIES="git libzip mysql-client curl libzip-dev zlib
  RUN  apk add libpng \
  && apk add php8-pdo \
  && apk add libpng-dev \
  && apk add ldb-dev libldap openldap-dev \
  && apk add libzip-dev \
  && apk add libxml2-dev \
  && apk add php8-dom \
  && apk add php8-xml \
  && apk add php8-xmlwriter \
  && apk add php8-fileinfo \
  && apk add php8-ldap \
  && apk add php8-tokenizer \
  && apk add php8-mongodb \
  && docker-php-ext-install gd \
  && docker-php-ext-install ldap \
  && docker-php-ext-install zip \
  && docker-php-ext-install soap \
  && docker-php-ext-install sockets \
  && docker-php-ext-install dom \
  && docker-php-ext-install xml \
  && docker-php-ext-install xmlwriter \
  && docker-php-ext-install fileinfo 
#  RUN docker-php-ext-install tokenizer

  RUN apk --no-cache update \
  && apk --no-cache upgrade
  RUN apk add --no-cache $PHPIZE_DEPS \
        freetype-dev \
        libjpeg-turbo-dev
#  RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-png-dir=/usr/include/
#  RUN docker-php-ext-install -j$(getconf _NPROCESSORS_ONLN) gd
  RUN docker-php-ext-configure gd --with-jpeg  --with-freetype
# --with-webp --with-xpm
  RUN docker-php-ext-install gd

#  docker-php-ext-configure gd --with-freetype-dir=/usr/lib/  --with-png-dir=/usr/lib/   --with-jpeg-dir=/usr/lib/ --with-gd