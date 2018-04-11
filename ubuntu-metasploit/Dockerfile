from ubuntu:16.04

MAINTAINER diodonfrost diodonfrost@protonmail.com

WORKDIR /opt

# Update package list
RUN apt update

# Install ruby
RUN apt install -y ruby ruby-dev

# Install dependency
RUN apt install -y autoconf \
  bison \
  build-essential \
  curl \
  git-core \
  libapr1 \
  libaprutil1 \
  libcurl4-openssl-dev \
  libgmp3-dev \
  libpcap-dev \
  libpq-dev \
  libreadline6-dev \
  libsqlite3-dev \
  libssl-dev \
  libsvn1 \
  libtool \
  libxml2 \
  libxml2-dev \
  libxslt-dev \
  libyaml-dev \
  locate \
  ncurses-dev \
  openssl \
  postgresql \
  postgresql-contrib \
  wget \
  xsel  \
  zlib1g \
  git \
  zlib1g-dev

# clone metasploit repository
RUN git clone https://github.com/rapid7/metasploit-framework /opt/metasploit-framework

WORKDIR /opt/metasploit-framework

# Install ruby dependency
RUN gem install bundle

RUN bundle install
