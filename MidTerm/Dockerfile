FROM nvcr.io/nvidia/cuda:12.2.2-cudnn8-devel-ubuntu22.04

#Set Timezone to CDT
ENV TZ=America/Chicago

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Update and upgrade the system
RUN apt-get -y update && apt-get -y upgrade

# Install python3 and pip
RUN apt-get update && apt-get install -y python3 python3-pip

# Install tensorflow
RUN pip3 install tensorflow

# Install jupyterlab
RUN pip3 install jupyterlab

# Install Packages to export Jupyter Notebooks to PDF
# RUN apt-get install -y texlive-xetex \
#    texlive-fonts-recommended \
#    #texlive-generic-recommended \
#    pandoc


# Install jupyterlab config file
COPY jupyter_notebook_config.py /root/.jupyter/


WORKDIR /workspace
EXPOSE 8888

# Start JupyterLab
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root", "--notebook-dir=/root/notebooks", "--NotebookApp.token=''", "--NotebookApp.password=''"]
