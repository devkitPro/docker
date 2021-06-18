FROM devkitpro/toolchain-base

MAINTAINER Dave Murphy <davem@devkitpro.org>

RUN dkp-pacman -Syyu --noconfirm gamecube-dev wii-dev wiiu-dev && \
    dkp-pacman -S --needed --noconfirm ppc-portlibs gamecube-portlibs wii-portlibs wiiu-portlibs && \
    dkp-pacman -S --needed --noconfirm devkitARM && \
    dkp-pacman -Scc --noconfirm

ENV DEVKITPPC=${DEVKITPRO}/devkitPPC
ENV DEVKITARM=/opt/devkitpro/devkitARM
