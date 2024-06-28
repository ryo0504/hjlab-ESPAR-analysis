FROM ubuntu:latest
RUN apt-get update && apt-get install -y \
    sudo \
    wget \
    vim
WORKDIR /opt
RUN wget https://repo.anaconda.com/archive/Anaconda3-2024.02-1-Linux-aarch64.sh && \
    bash Anaconda3-2024.02-1-Linux-aarch64.sh -b -p /opt/anaconda3 && \
    rm -f Anaconda3-2024.02-1-Linux-aarch64.sh
ENV PATH /opt/anaconda3/bin:$PATH

RUN pip install --upgrade pip

# %matplotlib widgetを使うため
RUN conda install -y -c conda-forge ipywidgets && \
    conda install -c conda-forge ipympl && \
    conda install -y -c conda-forge nodejs

WORKDIR /

CMD ["jupyter", "lab", "--ip=0.0.0.0", "--allow-root", "--LabApp.token=''"]