FROM qudi:createcondaenv

RUN conda init bash 
SHELL ["bash", "-lc"]
RUN conda activate qudi &&\
    python ./core/qudikernel.py install

CMD /bin/bash