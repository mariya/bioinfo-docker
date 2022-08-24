FROM ubuntu:focal

WORKDIR /src

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y \
  git \
  build-essential \
  zlib1g-dev \
  cmake

RUN git clone https://github.com/lbcb-sci/racon && \
  cd racon && \
  mkdir build && \
  cd build && \
  cmake -DCMAKE_BUILD_TYPE=Release .. && \
  make

ENV PATH=/src/racon/build/bin:$PATH
