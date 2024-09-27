FROM devkitpro/toolchain-base

MAINTAINER Dave Murphy <davem@devkitpro.org>

ENV DEBIAN_FRONTEND=noninteractive

RUN dkp-pacman -Syyu --noconfirm && \
    apt-get update && apt-get upgrade -y && apt-get install -y python3-venv && wget https://leddaz.github.io/files/makerom && \
    chmod a+x makerom && cp makerom /usr/local/bin && \
    dkp-pacman -S --needed --noconfirm 3ds-dev nds-dev gp32-dev gba-dev gp2x-dev && \
    dkp-pacman -S --needed --noconfirm 3ds-portlibs nds-portlibs armv4t-portlibs && \
    yes | dkp-pacman -Scc

ENV DEVKITARM=${DEVKITPRO}/devkitARM
