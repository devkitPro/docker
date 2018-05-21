FROM debian:stretch

MAINTAINER Dave Murphy <davem@devkitpro.org>

ARG DEBIAN_FRONTEND=noninteractive


RUN apt-get update && apt-get install -y apt-utils
RUN apt-get install -y pkg-config curl wget bzip2 xz-utils make git bsdtar doxygen sudo gnupg

RUN wget https://github.com/devkitPro/pacman/releases/download/devkitpro-pacman-1.0.1/devkitpro-pacman.deb

RUN dpkg -i devkitpro-pacman.deb && rm devkitpro-pacman.deb
