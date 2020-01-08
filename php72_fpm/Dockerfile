FROM daocloud.io/library/php:7.2-fpm
LABEL maintainer="captain_jackie@sina.com" \
      version="1.0" \
      description="php-fpm image"
RUN echo "" \
    && apt-get update \
    && apt-get install -y vim \
    && apt-get install -y wget \
    && apt-get install -y unzip \
    && echo "set hlsearch" > ~/.vimrc \
    && apt-get install -y \
    	libfreetype6-dev \
    	libjpeg62-turbo-dev \
    	libmcrypt-dev \
    	libpng-dev \
        libmcrypt4 \
        iputils-ping \
        procps \
        net-tools \
        libpcre++-dev \
        git \
    && pecl install mcrypt \
    && docker-php-ext-install iconv \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd \
    && docker-php-source extract \
    && cd /usr/src/php \
    && cp ./php.ini-development /usr/local/etc/php/conf.d/ \
    && mv /usr/local/etc/php/conf.d/php.ini-development /usr/local/etc/php/php.ini \
    && pecl install -a apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-install gettext \
    && pecl install igbinary \
    && docker-php-ext-enable igbinary \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && cd /usr/local/src \
    && wget http://download.icu-project.org/files/icu4c/51.2/icu4c-51_2-src.tgz \
    && tar zxvf icu4c-51_2-src.tgz \
    && cd /usr/local/src/icu/source \
    && ./configure && make && make install \
    && docker-php-ext-install intl \
    && cd /usr/local/src \
    && wget https://github.com/websupport-sk/pecl-memcache/archive/NON_BLOCKING_IO_php7.zip \
    && unzip NON_BLOCKING_IO_php7.zip \
    && cd pecl-memcache-NON_BLOCKING_IO_php7 \
    && /usr/local/bin/phpize \
    && ./configure --with-php-config=/usr/local/bin/php-config \
    && make && make install && docker-php-ext-enable memcache \
    && pecl install msgpack \
    && docker-php-ext-enable msgpack \
    && apt-get install -y libmemcached-dev libmemcached-tools \
    && pecl install memcached \
    && docker-php-ext-install pcntl \
    && docker-php-ext-install pdo_mysql \
    && apt-get install -y libghc-persistent-sqlite-dev \
    && docker-php-ext-install pdo_sqlite \
    && apt-get install -y libpspell-dev \
    && docker-php-ext-install pspell \
    && apt-get install -y librecode-dev \
    && docker-php-ext-install recode \
    && pecl install redis \
    && docker-php-ext-enable redis \
    && docker-php-ext-install shmop \
    && docker-php-ext-install sockets \
    && docker-php-ext-install sysvmsg \
    && docker-php-ext-install sysvsem \
    && docker-php-ext-install sysvshm \
    && apt-get install -y libtidy-dev \
    && docker-php-ext-install tidy \
    && apt-get install -y libxml2-dev \
    && docker-php-ext-install wddx \
    && docker-php-ext-install xmlrpc \
    && apt-get install -y libxslt1-dev \
    && docker-php-ext-install xsl \
    && pecl install yaf \
    && docker-php-ext-enable yaf \
    && docker-php-ext-install zip \
    && cd /usr/local/src \
    && wget https://openresty.org/download/openresty-1.15.8.1.tar.gz \
    && tar -xvf openresty-1.15.8.1.tar.gz \
    && wget https://www.openssl.org/source/openssl-1.1.0l.tar.gz \
    && tar -xvf openssl-1.1.0l.tar.gz \
    && cd openresty-1.15.8.1 \
    && ./configure --with-openssl=/usr/local/src/openssl-1.1.0l && make && make instal \
    && cd /usr/local/bin \
    && curl -sS https://getcomposer.org/installer | php \
    && mv /usr/local/bin/composer.phar /usr/local/bin/composerl
ENV OPENRESTY_HOME /usr/local/openresty
ENV PATH $OPENRESTY_HOME/bin:$PATH
CMD ["php-fpm"]

