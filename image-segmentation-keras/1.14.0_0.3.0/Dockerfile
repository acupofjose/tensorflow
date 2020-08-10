# Ubuntu 18.04, CUDA 10.0, Python 3.6
ARG DOCKER_REGISTRY=public.aml-repo.cms.waikato.ac.nz:443/
FROM ${DOCKER_REGISTRY}tensorflow/tensorflow:1.14.0-gpu-py3

RUN apt-get update && \
	apt-get install -y --no-install-recommends git-core wget libglib2.0-0 libsm6 libxrender-dev libxext6 && \
	rm -rf /var/lib/apt/lists/* && \
	pip install Cython && \
	pip install "opencv-python<4.2" && \
	pip install keras-segmentation && \
    pip uninstall -y numpy && \
    pip install "numpy<=1.17.4" && \
	rm -Rf /root/.cache/pip
	
COPY bash.bashrc /etc/bash.bashrc

WORKDIR /opt/keras-image-segmentation/