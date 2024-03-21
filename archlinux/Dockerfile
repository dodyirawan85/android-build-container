FROM archlinux:base-devel

WORKDIR /root/buildroot

# Initialize key
RUN pacman-key --init
RUN pacman-key --populate

# Update system and installing needed packages
RUN pacman -Syyu --noconfirm
RUN pacman -S --needed --noconfirm \
    bc \
    gdb \
    git \
    inetutils \
    lld \
    openssl-1.1 \
    python3 \
    repo

# Remove pacman cache and keys
RUN pacman -Scc
RUN rm -rf /etc/pacman.d/gnupg

# Run build script on container start
CMD ["bash", "./build.sh"]
