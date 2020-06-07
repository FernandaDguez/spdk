FROM debian:buster-20200514-slim

WORKDIR /root

RUN apt-get update \
    && apt-get install -y \
        git \
        nvme-cli \
        fio \
	&& git clone \
 	 --recursive \
	 --depth 1 \
 	 --shallow-submodules \
 	 --branch v20.04.1 \
 	 https://github.com/spdk/spdk \
	&& /root/spdk/scripts/pkgdep.sh \
	&& apt-get clean \
    	&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
	

