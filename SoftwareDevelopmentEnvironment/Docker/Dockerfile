FROM debian

MAINTAINER Abraham Arce <xe1gyq@gmail.com>

ENV TIMEZONE America/Mexico_City
ENV DEBIAN_FRONTEND noninteractive
ENV USER root

RUN     apt-get update && \
        apt-get -y upgrade && \
        apt-get -y install sudo && \
        rm -rf /var/lib/apt/lists/*

RUN     useradd -ms /bin/bash user && \
        echo "user:user" | chpasswd && \
        adduser user sudo

USER user
WORKDIR /home/user

CMD ["bash"]
