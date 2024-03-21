FROM ubuntu:20.04

WORKDIR /root/buildroot

# Update system packages
RUN apt update && apt upgrade -y

# Install required dependencies
RUN DEBIAN_FRONTEND=noninteractive \
    apt install \
    autoconf automake axel bc bison build-essential \
    ccache clang cmake curl expat flex g++ \
    g++-multilib gawk gcc gcc-multilib git git-lfs gnupg gperf \
    htop imagemagick lib32ncurses5-dev lib32z1-dev libtinfo5 libc6-dev libcap-dev \
    libexpat1-dev libgmp-dev '^liblz4-.*' '^liblzma.*' libmpc-dev libmpfr-dev libncurses5-dev \
    libsdl1.2-dev libssl-dev libtool libxml2 libxml2-utils '^lzma.*' lzop \
    maven ncftp ncurses-dev patch patchelf pkg-config pngcrush \
    pngquant python2.7 python-all-dev re2c schedtool squashfs-tools subversion \
    texinfo unzip w3m xsltproc zip zlib1g-dev lzip \
    libxml-simple-perl libswitch-perl apt-utils rsync \
    libncurses5 curl python-is-python3 -y

# Cleanup apt cache
RUN apt clean && rm -rf /var/lib/apt/lists/*

# Run build script on container start
CMD ["bash", "./build.sh"]
