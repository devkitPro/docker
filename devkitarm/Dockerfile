FROM devkitpro/toolchain-base

MAINTAINER Dave Murphy <davem@devkitpro.org>

ARG DEBIAN_FRONTEND=noninteractive

RUN  dkp-pacman -Syyu --noconfirm 3ds-dev nds-dev gp32-dev gba-dev

RUN sudo dkp-pacman -S --needed --noconfirm `dkp-pacman -Slq dkp-libs | grep '^3ds-'`
