FROM python:3.8

WORKDIR /src

RUN apt-get update && apt-get install -y \
  git

RUN pip install \
  biopython \
  bx-python \
  Cython

RUN git clone https://github.com/Magdoll/cDNA_Cupcake.git && \
  cd cDNA_Cupcake && \
  python setup.py build && \
  python setup.py install
