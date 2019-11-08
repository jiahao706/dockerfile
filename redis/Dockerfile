FROM daocloud.io/library/redis:3.2.8
LABEL maintainer="captain_jackie@sina.com" \
      version="1.0" \
      description="redis image"
RUN echo "" \
    && apt-get update \
    && apt-get install -y vim \
    && apt-get install -y wget \
    && apt-get install -y unzip \
    && apt-get install -y procps \
    && apt-get install -y net-tools \
    && echo "set hlsearch" > ~/.vimrc

