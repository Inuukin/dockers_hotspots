FROM python:3.9-slim
ENV DEBIAN_FRONTEND=noninteractive \
    KRAKEN_VERSION=2.1.3 
    
RUN apt-get update && \
    apt-get install -y \
        default-jdk \
        build-essential \
        libz-dev \
        wget \
        unzip && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
    
# Download and install Kraken2
RUN wget https://github.com/DerrickWood/kraken2/archive/refs/tags/v${KRAKEN_VERSION}.tar.gz &&\
    tar -xvzf v${KRAKEN_VERSION}.tar.gz \
    && rm v${KRAKEN_VERSION}.tar.gz \
    && cd kraken2-${KRAKEN_VERSION} \
    && ./install_kraken2.sh /usr/local/bin \
    && cd .. \
    && rm -rf kraken2-${KRAKEN_VERSION}
