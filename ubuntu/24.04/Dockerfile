FROM ubuntu:24.04

WORKDIR /root/buildroot

ENV DEBIAN_FRONTEND=noninteractive

# Update system packages
RUN apt update && apt upgrade -y

# Install required dependencies
RUN apt install -y \
    bc bison build-essential ccache \
    curl flex g++-multilib gcc-multilib \
    git git-lfs gnupg gperf imagemagick \
    protobuf-compiler python3-protobuf lib32readline-dev \
    lib32z1-dev libdw-dev libelf-dev libgnutls28-dev lz4 \
    libsdl1.2-dev libssl-dev libxml2 libxml2-utils lzop \
    pngcrush rsync schedtool squashfs-tools xsltproc xxd \
    zip zlib1g-dev wget nano

# LineageOS 20 and older requirements
RUN wget https://archive.ubuntu.com/ubuntu/pool/universe/n/ncurses/libtinfo5_6.3-2_amd64.deb && dpkg -i libtinfo5_6.3-2_amd64.deb && rm -f libtinfo5_6.3-2_amd64.deb
RUN wget https://archive.ubuntu.com/ubuntu/pool/universe/n/ncurses/libncurses5_6.3-2_amd64.deb && dpkg -i libncurses5_6.3-2_amd64.deb && rm -f libncurses5_6.3-2_amd64.deb

# Install repo tools
RUN curl https://storage.googleapis.com/git-repo-downloads/repo > /usr/local/bin/repo
RUN chmod a+x /usr/local/bin/repo

# Cleanup apt cache
RUN apt clean && rm -rf /var/lib/apt/lists/*
