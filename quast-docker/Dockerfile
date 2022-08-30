FROM continuumio/miniconda3

WORKDIR /src

# Create Conda environment from the YAML file
COPY conda.yml .
RUN conda env create -f conda.yml

# Override default shell and use bash
SHELL ["conda", "run", "-n", "env", "/bin/bash", "-c"]

RUN echo "source activate env" > ~/.bashrc
ENV PATH /opt/conda/envs/env/bin/:$PATH
