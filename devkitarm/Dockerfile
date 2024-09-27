FROM devkitpro/toolchain-base

MAINTAINER Leonardo Ledda <leonardoledda@gmail.com>

ENV DEBIAN_FRONTEND=noninteractive

RUN dkp-pacman -Syyu --noconfirm && \
    apt-get update && apt-get upgrade -y && apt-get install -y build-essential git python3-venv && \
    git clone --depth=1 https://github.com/3DSGuy/Project_CTR && cd Project_CTR && make && \
    cp makerom/bin/makerom /usr/local/bin/makerom && cd .. && rm -rf Project_CTR && \
    dkp-pacman -S --needed --noconfirm 3ds-dev nds-dev gp32-dev gba-dev gp2x-dev && \
    dkp-pacman -S --needed --noconfirm 3ds-portlibs nds-portlibs armv4t-portlibs && \
    yes | dkp-pacman -Scc

ENV DEVKITARM=${DEVKITPRO}/devkitARM
