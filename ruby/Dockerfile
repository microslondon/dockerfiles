FROM debian:wheezy

ENV RUBY_VERSION_MAJOR 2.1
ENV RUBY_VERSION 2.1.1

RUN apt-get update && apt-get -y install \
  procps \
  build-essential \
  wget \
  libreadline6 \
  libreadline6-dev \
  zlib1g \
  zlib1g-dev \
  libssl-dev \
  libyaml-dev \
  libsqlite3-dev \
  libxml2-dev \
  libxslt-dev \
  libpq-dev \
  libcurl3-dev

RUN cd /usr/local/src && \
  mkdir ruby && \
  cd ruby && \
  wget http://cache.ruby-lang.org/pub/ruby/$RUBY_VERSION_MAJOR/ruby-$RUBY_VERSION.tar.gz && \
  tar -xzvf ruby-$RUBY_VERSION.tar.gz && \
  cd ruby-$RUBY_VERSION && \
  ./configure && \
  make && \
  make install && \
  rm -rf /usr/local/src/ruby && \
  echo "gem: --no-document" > ~/.gemrc

RUN gem install bundler
