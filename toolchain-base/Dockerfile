FROM debian:stretch-slim

MAINTAINER Dave Murphy <davem@devkitpro.org>

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y --no-install-recommends apt-utils && \
    apt-get install -y --no-install-recommends sudo ca-certificates pkg-config curl wget bzip2 xz-utils make git bsdtar doxygen gnupg && \
    apt-get install -y --no-install-recommends gdebi-core && \
    apt-get install -y --no-install-recommends cmake && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN wget https://github.com/devkitPro/pacman/releases/latest/download/devkitpro-pacman.amd64.deb && \
    gdebi -n devkitpro-pacman.amd64.deb && \
    rm devkitpro-pacman.amd64.deb && \
    dkp-pacman -Scc --noconfirm

ENV DEVKITPRO=/opt/devkitpro
ENV PATH=${DEVKITPRO}/tools/bin:$PATH
