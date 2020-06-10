FROM cn007b/debian:buster

MAINTAINER V. Kovpak <cn007b@gmail.com>

RUN apt-get update --fix-missing

# python
RUN apt install -y \
  libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev \
  tk-dev libgdbm-dev libc6-dev libbz2-dev libffi-dev zlib1g-dev
RUN \
  cd /usr/src \
  && wget https://www.python.org/ftp/python/3.7.7/Python-3.7.7.tgz \
  && tar xzf Python-3.7.7.tgz \
  && cd Python-3.7.7 \
  && ./configure --enable-optimizations \
  && make altinstall

# pip
RUN apt-get install -y python3-pip

RUN pip3 install virtualenv
