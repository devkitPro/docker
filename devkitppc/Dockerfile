FROM devkitpro/toolchain-base

MAINTAINER Dave Murphy <davem@devkitpro.org>

RUN dkp-pacman -Syyu --noconfirm gamecube-dev wii-dev && \
    dkp-pacman -S --needed --noconfirm `dkp-pacman -Slq dkp-libs | grep '^ppc-'` && \
    dkp-pacman -Scc --noconfirm
ENV DEVKITPPC=${DEVKITPRO}/devkitPPC
