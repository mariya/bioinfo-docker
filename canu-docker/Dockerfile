FROM ubuntu:focal

WORKDIR /src

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y \
  curl \
  xz-utils \
  libfindbin-libs-perl \
  libgomp1 \
  default-jre \
  gnuplot

RUN curl -L https://github.com/marbl/canu/releases/download/v2.2/canu-2.2.Linux-amd64.tar.xz --output canu-2.2.Linux.tar.xz &&\
  tar -xJf canu-2.2.*.tar.xz

ENV PATH=/src/canu-2.2/bin:$PATH
