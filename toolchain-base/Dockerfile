FROM debian:buster-slim

MAINTAINER Dave Murphy <davem@devkitpro.org>

ENV DEBIAN_FRONTEND=noninteractive

RUN echo "deb http://deb.debian.org/debian buster-backports main" > /etc/apt/sources.list.d/buster-backports.list && \
    apt-get update && apt-get upgrade -y && \
    apt-get install -y --no-install-recommends apt-utils && \
    apt-get install -y --no-install-recommends sudo ca-certificates pkg-config curl wget bzip2 xz-utils make bsdtar doxygen gnupg && \
    apt-get install -y --no-install-recommends git git-restore-mtime && \
    apt-get install -y --no-install-recommends cmake/buster-backports zip unzip && \
    apt-get install -y --no-install-recommends locales && \
    apt-get install -y --no-install-recommends patch && \
    sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=en_US.UTF-8 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN wget https://apt.devkitpro.org/install-devkitpro-pacman && \
    chmod +x ./install-devkitpro-pacman && \
    ./install-devkitpro-pacman && \
    rm ./install-devkitpro-pacman && \
    yes | dkp-pacman -Scc

ENV LANG en_US.UTF-8

ENV DEVKITPRO=/opt/devkitpro
ENV PATH=${DEVKITPRO}/tools/bin:$PATH
