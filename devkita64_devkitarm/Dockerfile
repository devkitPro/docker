FROM devkitpro/devkita64

MAINTAINER Dave Murphy <davem@devkitpro.org>

RUN dkp-pacman -Sy --noconfirm devkitARM devkitarm-rules && \
    dkp-pacman -Scc --noconfirm

ENV DEVKITARM=/opt/devkitpro/devkitARM
