FROM ubuntu:focal

WORKDIR /src

RUN apt-get update && apt-get install -y \
  wget \
  bzip2 \
  build-essential \
  zlib1g-dev \
  libbz2-dev \
  liblzma-dev

RUN wget https://github.com/samtools/bcftools/releases/download/1.15.1/bcftools-1.15.1.tar.bz2 && \
  bzip2 -d bcftools-1.15.1.tar.bz2 && \
  tar -xvf bcftools-1.15.1.tar
RUN cd /src/bcftools-1.15.1 && ./configure --prefix=/src/bcftools && make && make install

ENV PATH=/src/bcftools/bin:$PATH
