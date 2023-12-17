FROM qudi:debian-stable

# Make RUN commands use `bash --login`:
# SHELL ["/bin/bash", "--login", "-c"]

RUN apt-get update
RUN apt-get install -y ffmpeg libsm6 libxext6
RUN apt-get install -y wget
RUN mkdir -p /miniconda3
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O /miniconda3/miniconda.sh
RUN bash  /miniconda3/miniconda.sh -b -u -p /miniconda3
RUN rm -rf /miniconda3/miniconda.sh
RUN /miniconda3/bin/conda init bash
# RUN /miniconda3/bin/conda init zsh
RUN /miniconda3/bin/conda config --add channels conda-forge
RUN /miniconda3/bin/conda config --set channel_priority strict
RUN /miniconda3/bin/conda env create -f /qudi/tools/conda-env-linx64-qt5.yml

# RUN echo "/miniconda3/bin/conda activate qudi" > /etc/bash.bashrc
SHELL ["/miniconda3/bin/conda", "run", "-n", "qudi", "/bin/bash", "-c"]
RUN python core/qudikernel.py install

ENV LIBGL_ALWAYS_INDIRECT=0

ENV DISPLAY=172.22.0.1:0.0
