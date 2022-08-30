FROM python:3.8

WORKDIR /src

RUN apt-get update && apt-get install -y \
  git \
  pkg-config \
  libfreetype6-dev \
  libpng-dev \
  python3-matplotlib \
  zlib1g-dev

RUN pip install quast
