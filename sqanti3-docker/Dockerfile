# Instructions: https://github.com/ConesaLab/SQANTI3/wiki/Dependencies-and-installation

FROM continuumio/miniconda3

WORKDIR /src

RUN apt-get update && apt-get install -y \
  wget \
  libcurl4

RUN wget https://github.com/ConesaLab/SQANTI3/archive/refs/tags/v5.0.tar.gz && \
  tar -xvf v5.0.tar.gz && \
  cd SQANTI3-5.0 && \
  conda env create -f SQANTI3.conda_env.yml

# Override default shell and use bash
SHELL ["conda", "run", "-n", "SQANTI3.env", "/bin/bash", "-c"]

RUN wget http://hgdownload.cse.ucsc.edu/admin/exe/linux.x86_64/gtfToGenePred -P /src/SQANTI3-5.0/utilities/
RUN chmod +x /src/SQANTI3-5.0/utilities/gtfToGenePred

RUN source activate SQANTI3.env && \
  git clone https://github.com/Magdoll/cDNA_Cupcake.git && \
  cd cDNA_Cupcake && \
  python setup.py build && \
  python setup.py install

ENV PYTHONPATH=/src/cDNA_Cupcake/sequence/:$PYTHONPATH
ENV PYTHONPATH=/src/cDNA_Cupcake/:$PYTHONPATH

RUN echo "source activate SQANTI3.env" > ~/.bashrc
ENV PATH /opt/conda/envs/SQANTI3.env/bin/:$PATH
