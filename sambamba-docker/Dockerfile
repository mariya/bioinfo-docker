FROM ubuntu:focal

WORKDIR /src

RUN apt-get update && apt-get install -y \
  wget \
  xz-utils \
  git \
  build-essential \
  python3 \
  zlib1g-dev \
  liblz4-dev

RUN wget https://github.com/ldc-developers/ldc/releases/download/v1.7.0/ldc2-1.7.0-linux-x86_64.tar.xz && \
  tar xvJf ldc2-1.7.0-linux-x86_64.tar.xz

ENV PATH=/src/ldc2-1.7.0-linux-x86_64/bin:$PATH
ENV LIBRARY_PATH=/src/ldc2-1.7.0-linux-x86_64/lib

RUN git clone --recursive https://github.com/biod/sambamba.git && \
  cd sambamba && make && make check

ENV PATH=/src/sambamba/bin:$PATH
