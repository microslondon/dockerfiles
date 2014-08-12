FROM debian:wheezy

ENV NODE_VERSION 0.10.30

RUN apt-get update && apt-get -y install \
  procps \
  build-essential \
  python \
  wget

RUN cd /usr/local/src && \
  mkdir node && \
  cd node && \
  wget http://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION.tar.gz && \
  tar -xzvf node-v$NODE_VERSION.tar.gz && \
  cd node-v$NODE_VERSION && \
  ./configure && \
  make && \
  make install && \
  rm -rf /usr/local/src/node

RUN npm install forever -g
