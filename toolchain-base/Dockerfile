FROM debian:bookworm-slim

LABEL maintainer="devkitPro developers support@devkitpro.org"

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y --no-install-recommends apt-utils && \
    apt-get install -y --no-install-recommends sudo ca-certificates pkg-config curl wget bzip2 xz-utils make libarchive-tools doxygen gnupg && \
    apt-get install -y --no-install-recommends git git-restore-mtime && \
    apt-get install -y --no-install-recommends rsync && \
    apt-get install -y --no-install-recommends zip unzip ninja-build && \
    apt-get install -y --no-install-recommends python3 python-is-python3 python3-lz4 && \
    apt-get install -y --no-install-recommends locales && \
    apt-get install -y --no-install-recommends patch && \
    echo "deb http://deb.debian.org/debian bookworm-backports main" >> /etc/apt/sources.list.d/bookworm-backports.list && \
    apt update && \
    apt-get install -y --no-install-recommends -t bookworm-backports cmake && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    echo -n "UTC" > /etc/timezone && \
    apt-get -y autoremove --purge && \
    apt-get -y clean && \
    dpkg-reconfigure -f noninteractive tzdata && \
    apt-get -y purge locales-all && \
    dpkg-reconfigure -f noninteractive locales && \
    echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
    echo "en_US.UTF-8 UTF-8" > /etc/default/locale && \
    locale-gen en_US.UTF-8 && \
    update-locale

RUN ln -s /proc/mounts /etc/mtab && \
    wget https://apt.devkitpro.org/install-devkitpro-pacman && \
    chmod +x ./install-devkitpro-pacman && \
    ./install-devkitpro-pacman && \
    rm ./install-devkitpro-pacman && \
    dkp-pacman -Syyu --noconfirm && \
    dkp-pacman -S --needed --noconfirm dkp-toolchain-vars dkp-meson-scripts && \
    yes | dkp-pacman -Scc


ENV LANG=en_US.UTF-8

ENV DEVKITPRO=/opt/devkitpro
ENV PATH=${DEVKITPRO}/tools/bin:$PATH
