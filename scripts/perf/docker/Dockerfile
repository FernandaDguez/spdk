FROM debian:buster-20200514-slim

RUN apt-get update \
    && apt-get install -y \
        git \
        nvme-cli \
        build-essential


WORKDIR /root

# Clone the fio repo
RUN git clone https://github.com/axboe/fio
RUN cd fio/ && ./configure && make

# Clone the SPDK repo
RUN git clone https://github.com/spdk/spdk.git
RUN git -C /root/spdk submodule update --init

## Install dependencies for SPDK
RUN /root/spdk/scripts/pkgdep.sh

# Clean Up
RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
