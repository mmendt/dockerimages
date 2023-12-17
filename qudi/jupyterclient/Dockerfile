FROM continuumio/miniconda3

WORKDIR /jupyterforqudi/

COPY . .

RUN apt-get update
RUN conda update conda -y
RUN conda create -y --name jupyterforqudi python=3.6
RUN conda config --add channels conda-forge
RUN conda config --set channel_priority strict
RUN echo "conda activate jupyterforqudi" >> ~/.bashrc
SHELL ["/bin/bash", "--login", "-c"]
RUN conda install -y rpyc numpy jupyter
RUN pip install ruamel.yaml
RUN python /jupyterforqudi/qudikernel.py install


CMD /bin/bash