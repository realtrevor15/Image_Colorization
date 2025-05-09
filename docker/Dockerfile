FROM continuumio/miniconda3

COPY ./install/docker_conda_install.sh /app/install/
WORKDIR /app/install/

# RUN conda init
RUN conda create -n env python=3.6
RUN echo "source activate env" > ~/.bashrc
ENV PATH /opt/conda/envs/env/bin:$PATH

RUN ./docker_conda_install.sh

COPY . /app
WORKDIR /app

RUN apt install -y curl
CMD ["python","ideepcolor_docker.py"]
