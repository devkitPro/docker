FROM devkitpro/toolchain-base

MAINTAINER Dave Murphy <davem@devkitpro.org>

ARG DEBIAN_FRONTEND=noninteractive

RUN dkp-pacman -Syyu --noconfirm switch-dev

RUN sudo dkp-pacman -S --needed --noconfirm `dkp-pacman -Slq dkp-libs | grep '^switch-'`
