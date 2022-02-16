FROM devkitpro/toolchain-base

MAINTAINER Dave Murphy <davem@devkitpro.org>

RUN dkp-pacman -Syyu --noconfirm 3ds-dev nds-dev gp32-dev gba-dev gp2x-dev && \
    dkp-pacman -S --needed --noconfirm 3ds-portlibs nds-portlibs armv4t-portlibs && \
    yes | dkp-pacman -Scc

ENV DEVKITARM=${DEVKITPRO}/devkitARM
