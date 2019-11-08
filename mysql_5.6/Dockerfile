FROM daocloud.io/library/mysql:5.6.35
LABEL maintainer="captain_jackie@sina.com" \
      version="1.0" \
      description="mysql image"
ENV MYSQL_ROOT_PASSWORD=dongjiahao
ENV MYSQL_DATABASE=class
ENV MYSQL_USER=dongjiahao
ENV MYSQL_PASSWORD=dongjiahao
ENV MYSQL_ALLOW_EMPTY_PASSWORD=no
RUN echo "" \
    && apt-get update \
    && apt-get install -y vim \
    && apt-get install -y wget \
    && apt-get install -y unzip \
    && apt-get install -y procps \
    && apt-get install -y net-tools \
    && echo "set hlsearch" > ~/.vimrc
