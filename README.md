# ITAI-3377

This contains the docker containers for each modules as well as the Jupyter notbooks and submitted files.


Each folder contains an individual Dockerfile and a launch file for both Windows and Linux.  Module04 only contains the python files for this modules assignments

The modules have been tested on Windows using WSL and Docker Desktop as well as Ubuntu Linux.  The base image is the NVCR CUDNN8 for Cuda 12, and is configured to use an NVidia GPU.  These have been tested on RTX3090, A1000 and A2000 GPUS.

