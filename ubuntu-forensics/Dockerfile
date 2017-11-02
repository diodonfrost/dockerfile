from ubuntu

MAINTAINER diodonfrost diodonfrost@protonmail.com

# Install packages from apt repository
USER root
RUN apt update && apt install -y automake build-essential git ipython \
  libbz2-dev libc6-dev libfreetype6-dev libgdbm-dev libjansson-dev libjpeg8-dev \
  libmagic-dev libreadline-gplv2-dev libtool python2.7 python-dev python-pillow \
  python-pip tar unzip wget zlib1g zlib1g-dev testdisk vim nmap whois \
  libimage-exiftool-perl bsdmainutils tree

# Install additional dependencies
RUN pip install --upgrade pip
RUN pip install distorm3 openpyxl pycrypto pytz

# Install volatility
RUN git clone https://github.com/volatilityfoundation/volatility.git /opt/volatility

WORKDIR /opt/volatility

RUN python setup.py install

RUN mkdir /tmp/share
