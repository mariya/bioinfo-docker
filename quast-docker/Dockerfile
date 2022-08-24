FROM python:3.8

WORKDIR /src

RUN apt-get update && apt-get install -y \
  git \
  pkg-config \
  libfreetype6-dev \
  libpng-dev \
  python3-matplotlib \
  zlib1g-dev

RUN git clone https://github.com/ablab/quast && \
  cd quast && \
  ./setup.py install_full

ENV PATH=/usr/local/bin/:$PATH
