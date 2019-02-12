FROM devkitpro/toolchain-base

MAINTAINER Dave Murphy <davem@devkitpro.org>

RUN dkp-pacman -Syyu --noconfirm 3ds-dev nds-dev gp32-dev gba-dev nds-portlibs && \
    dkp-pacman -S --needed --noconfirm `dkp-pacman -Slq dkp-libs | grep '^3ds-'` && \
    dkp-pacman -Scc --noconfirm
ENV DEVKITARM=${DEVKITPRO}/devkitARM
