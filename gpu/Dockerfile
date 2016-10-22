# Based off of Kai's Dockerfile
# Adds a couple of useful tools in to make it dev ready 

# Start with cuDNN base image
FROM nvidia/cuda:8.0-cudnn5-devel
MAINTAINER Nikhil Mitra <nikhil.mitra@columbia.edu>

# Install git, wget, python-dev, pip and other dependencies
RUN apt-get update && apt-get install -y \
  git \
  wget \
  libopenblas-dev \
  python-dev \
  python-pip \
  python-nose

# For SciPy
RUN apt-get install -y libblas-dev liblapack-dev libatlas-base-dev gfortran

RUN pip install numpy
RUN pip install scipy

# Set CUDA_ROOT
ENV CUDA_ROOT /usr/local/cuda/bin
# Install bleeding-edge Theano
RUN pip install --upgrade --no-deps git+git://github.com/Theano/Theano.git
# Set up .theanorc for CUDA
RUN echo "[global]\ndevice=gpu\nfloatX=float32\noptimizer_including=cudnn\n[lib]\ncnmem=0.1\n[nvcc]\nfastmath=True" > /root/.theanorc

RUN pip install jupyter
RUN pip install ipython
RUN apt-get install htop
RUN pip install --user nose-parameterized

EXPOSE 8888
