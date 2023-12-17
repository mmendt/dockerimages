FROM simple_miniconda3_env

WORKDIR /home/

RUN conda config --add channels conda-forge &&\
    conda config --set channel_priority strict &&\
    conda install -y qutip && \
    conda install -y jupyter && \
    conda install -y matplotlib 





