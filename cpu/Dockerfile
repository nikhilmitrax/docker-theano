# Based off of Kai's Dockerfile
# Adds a couple of useful tools in to make it dev ready 


# Start with Ubuntu base image
FROM ubuntu:14.04
MAINTAINER Nikhil Mitra <nikhil.mitra@columbia.edu>

# Install build-essential, git, wget, python-dev, pip and other dependencies
RUN apt-get update && apt-get install -y \
  build-essential \
  git \
  wget \
  libopenblas-dev \
  python-dev \
  python-pip \
  python-nose \
  python-numpy \
  python-scipy

# For SciPy
RUN apt-get install -y libblas-dev liblapack-dev libatlas-base-dev gfortran

RUN pip install numpy
RUN pip install scipy

# Install bleeding-edge Theano
RUN pip install --upgrade --no-deps git+git://github.com/Theano/Theano.git

# Install usefuld tidbits
RUN pip install jupyter
RUN pip install ipython
RUN apt-get install htop
RUN pip install --user nose-parameterized

EXPOSE 8888