FROM devkitpro/toolchain-base

MAINTAINER Dave Murphy <davem@devkitpro.org>

RUN dkp-pacman -Syyu --noconfirm && \
    dkp-pacman -S --needed --noconfirm switch-dev && \
    dkp-pacman -S --needed --noconfirm switch-portlibs && \
    dkp-pacman -S --needed --noconfirm devkitARM && \
    dkp-pacman -S --needed --noconfirm dkp-toolchain-vars && \
    yes | dkp-pacman -Scc

ENV DEVKITARM=/opt/devkitpro/devkitARM
