FROM ubuntu:focal

WORKDIR /src

RUN apt-get update && apt-get install -y \
  wget \
  bzip2 \
  build-essential \
  libncurses5-dev \
  zlib1g-dev \
  libbz2-dev \
  liblzma-dev

RUN wget https://github.com/samtools/samtools/releases/download/1.15.1/samtools-1.15.1.tar.bz2 && \
  bzip2 -d samtools-1.15.1.tar.bz2 && \
  tar -xvf samtools-1.15.1.tar
RUN cd /src/samtools-1.15.1 && ./configure --prefix=/src/samtools && make && make install

ENV PATH=/src/samtools/bin:$PATH
