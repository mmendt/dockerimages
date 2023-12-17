FROM qudi:onlyfiles

RUN apt-get update
RUN apt-get install -y ffmpeg libsm6 libxext6
RUN conda config --add channels conda-forge
RUN conda config --set channel_priority strict
RUN conda env create -f /qudi/tools/conda-env-linx64-qt5.yml
RUN echo "conda activate qudi" >> ~/.bashrc
SHELL ["/bin/bash", "--login", "-c"]
RUN python core/qudikernel.py install

EXPOSE 12345

ENV LIBGL_ALWAYS_INDIRECT=0

ENV DISPLAY=172.22.0.1:0.0