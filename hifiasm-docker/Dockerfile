FROM ubuntu:focal

WORKDIR /src

RUN apt-get update && apt-get install -y \
  git \
  build-essential \
  zlib1g-dev

RUN git clone https://github.com/chhylp123/hifiasm && \
  cd hifiasm && make

ENV PATH=/src/hifiasm:$PATH
