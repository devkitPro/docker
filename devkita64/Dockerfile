FROM devkitpro/toolchain-base

MAINTAINER Dave Murphy <davem@devkitpro.org>

RUN dkp-pacman -Syyu --noconfirm switch-dev && \
    dkp-pacman -S --needed --noconfirm switch-portlibs && \
    dkp-pacman -S --needed --noconfirm devkitARM && \
    dkp-pacman -Scc --noconfirm

ENV DEVKITARM=/opt/devkitpro/devkitARM

