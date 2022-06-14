FROM continuumio/miniconda3

WORKDIR /src

RUN apt-get update && apt-get install -y \
  curl

# Create Conda environment from the YAML file
COPY conda.yml .
RUN conda env create -f conda.yml

# Override default shell and use bash
SHELL ["conda", "run", "-n", "env", "/bin/bash", "-c"]
