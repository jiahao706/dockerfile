FROM nginx
LABEL maintainer="captain_jackie@sina.com" \
      version="1.0" \
      description="nginx image"
RUN echo "" \
    && apt-get update \
    && apt-get install -y vim \
    && apt-get install -y wget \
    && apt-get install -y unzip \
    && apt-get install -y procps \
    && apt-get install -y net-tools \
    && echo "set hlsearch" > ~/.vimrc
