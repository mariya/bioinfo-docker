FROM continuumio/miniconda3

WORKDIR /src

# Create Conda environment from the YAML file
COPY conda.yml .
RUN conda env create -f conda.yml

# Override default shell and use bash
SHELL ["conda", "run", "-n", "env", "/bin/bash", "-c"]

RUN echo "source activate env" > ~/.bashrc
ENV PATH /opt/conda/envs/env/bin/:$PATH
RUN mkdir /opt/conda/envs/env/lib/python3.10/site-packages/quast_libs/red && \
  ln -s /opt/conda/envs/env/bin/Red /opt/conda/envs/env/lib/python3.10/site-packages/quast_libs/red/Red

RUN apt-get update && apt-get install -y time
RUN quast-download-gridss
# RUN quast-download-silva
# RUN quast-download-busco
