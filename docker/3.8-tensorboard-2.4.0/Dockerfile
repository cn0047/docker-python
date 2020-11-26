FROM cn007b/debian:buster

MAINTAINER V. Kovpak <cn007b@gmail.com>

RUN apt-get update --fix-missing

ARG PythonVer=3.8
ARG PythonVersion=3.8.5

# python
RUN apt install -y \
  libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev \
  tk-dev libgdbm-dev libc6-dev libbz2-dev libffi-dev zlib1g-dev
RUN \
  cd /usr/src \
  && wget https://www.python.org/ftp/python/$PythonVersion/Python-$PythonVersion.tgz \
  && tar xzf Python-$PythonVersion.tgz && rm Python-$PythonVersion.tgz \
  && cd Python-$PythonVersion \
  && ./configure --enable-optimizations \
  && make altinstall \
  && ln -s /usr/local/bin/python$PythonVer /usr/local/bin/python3

# pip
RUN \
  wget https://bootstrap.pypa.io/get-pip.py \
  && python$PythonVer get-pip.py && rm get-pip.py

# tensorboard
RUN pip3 install tensorboard==2.4.0
