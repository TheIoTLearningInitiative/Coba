FROM debian

MAINTAINER Abraham Arce <xe1gyq@gmail.com>

ENV TIMEZONE America/Mexico_City
ENV DEBIAN_FRONTEND noninteractive
ENV USER root

RUN     echo "deb http://ftp.us.debian.org/debian/ stretch main contrib non-free" >> /etc/apt/sources.list
RUN     echo "deb-src http://ftp.us.debian.org/debian/ stretch main contrib non-free" >> /etc/apt/sources.list

RUN     apt-get update && \
        apt-get -y upgrade && \
        apt-get -y install \
            # bc \
            build-essential \
            git \
            libelf-dev \
            libncurses5 \
            libncurses5-dev \
            libssl-dev \
            # linux-headers-$(uname -r) \
            #fakeroot \
            # kernel-package \
            sudo \
            #xz-utils && \
        rm -rf /var/lib/apt/lists/*

RUN     useradd -ms /bin/bash user && \
        echo "user:user" | chpasswd && \
        adduser user sudo

USER user
WORKDIR /home/user

RUN     git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git

CMD ["/bin/bash"]
