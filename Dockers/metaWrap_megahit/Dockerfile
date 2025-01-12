# Use the specified Miniconda base image
FROM continuumio/miniconda3:24.11.1-0

# Add additional channels to conda configuration
RUN conda config --add channels conda-forge && \
    conda config --add channels bioconda && \
    conda config --add channels default && \
    conda config --add channels ursky

# install mamba (replaces conda, but much faster):
RUN conda install -y mamba 
 
# install metawrap:
RUN mamba create -y --name metawrap-env --channel ursky metawrap-mg=1.3.2 megahit=1.1.3

# To fix the CONCOCT endless warning messages in metaWRAP=1.2+, run
RUN conda install -y blas=2.5=mkl

