# Image for very old oe-builds
#
# to build/push change in this directory and enter
# docker build --tag oe-build-image:ubuntu-16.04 .
# docker login docker.io
# docker push oe-build-image:ubuntu-16.04 schnitzeltony/oe-build-image:ubuntu-16.04

FROM docker.io/ubuntu:16.04

MAINTAINER Andreas Müller <schnitzeltony@gmail.com>

RUN apt-get update -y && apt-get install -y \
    software-properties-common \
    build-essential \
    dialog \
    apt-utils \
    manpages \
    git \
    man-db \
    git-man \
    gawk \
    diffstat \
    texinfo \
    chrpath \
    python2.7 python2.7-dev \
    python3.5 python3.5-dev \
    wget \
    gettext \
    realpath \
    make \
    bzip2 \
    cpio \
    ftp \
    sed \
    jq \
    sqlite3 \
    iputils-ping \
    gcc-4.9

RUN ln -sf /usr/bin/gcc-4.9 /usr/bin/gcc
RUN gcc -v

ENTRYPOINT ["/bin/bash"]
