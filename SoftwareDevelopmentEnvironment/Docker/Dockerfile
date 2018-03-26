FROM debian

MAINTAINER Abraham Arce <xe1gyq@gmail.com>

ENV TIMEZONE America/Mexico_City
ENV DEBIAN_FRONTEND noninteractive
ENV USER root


RUN     cat << EOM >> /etc/apt/sources.list \
            deb http://ftp.us.debian.org/debian/ stretch main contrib non-free \
            deb-src http://ftp.us.debian.org/debian/ stretch main contrib non-free \
            deb http://deb.debian.org/debian stretch main \
            deb-src http://deb.debian.org/debian stretch main \
        EOM

RUN     echo "deb http://ftp.us.debian.org/debian/ stretch main contrib non-free" >> /etc/apt/sources.list
RUN     echo "deb-src http://ftp.us.debian.org/debian/ stretch main contrib non-free" >> /etc/apt/sources.list

RUN     echo "deb http://deb.debian.org/debian stretch main" >> /etc/apt/sources.list
RUN     echo "deb-src http://deb.debian.org/debian stretch main" >> /etc/apt/sources.list
RUN     echo "deb http://deb.debian.org/debian stretch-updates main" >> /etc/apt/sources.list
RUN     echo "deb-src http://deb.debian.org/debian stretch-updates main" >> /etc/apt/sources.list
RUN     echo "deb http://security.debian.org/debian-security/ stretch/updates main" >> /etc/apt/sources.list
RUN     echo "deb-src http://security.debian.org/debian-security/ stretch/updates main" >> /etc/apt/sources.list

RUN     echo "deb http://deb.debian.org/debian stretch main contrib non-free" >> /etc/apt/sources.list
RUN     echo "deb-src http://deb.debian.org/debian stretch main contrib non-free" >> /etc/apt/sources.list
RUN     echo "deb http://deb.debian.org/debian stretch-updates main contrib non-free" >> /etc/apt/sources.list
RUN     echo "deb-src http://deb.debian.org/debian stretch-updates main contrib non-free" >> /etc/apt/sources.list
RUN     echo "deb http://security.debian.org/debian-security/ stretch/updates main contrib non-free" >> /etc/apt/sources.list
RUN     echo "deb-src http://security.debian.org/debian-security/ stretch/updates main contrib non-free" >> /etc/apt/sources.list

RUN     apt-get update && \
        apt-get -y upgrade && \
        apt-get -y install \
            bc \
            bison \
            build-essential \
            flex \
            git \
            libelf-dev \
            libncurses5 \
            libncurses5-dev \
            libssl-dev \
            # linux-headers-$(uname -r) \
            #fakeroot \
            # kernel-package \
            sudo && \
            #xz-utils && \
        rm -rf /var/lib/apt/lists/*

RUN     useradd -ms /bin/bash user && \
        echo "user:user" | chpasswd && \
        adduser user sudo

USER user
WORKDIR /home/user

RUN     git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git

CMD ["/bin/bash"]
