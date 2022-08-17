FROM python:3.8

WORKDIR /src

RUN apt-get update && apt-get install -y \
  git

RUN git clone  https://github.com/rrwick/Porechop.git && \
  cd Porechop && \
  python3 setup.py install

ENTRYPOINT ["/usr/local/bin/porechop"]
