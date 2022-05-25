# Image for qt4 qt-creator
#
# to build/push change in this directory and enter
# docker build --tag fedora-qt4:20 .
# docker login docker.io
# docker push fedora-qt4:20 schnitzeltony/fedora-qt4:20

FROM docker.io/fedora:20

MAINTAINER Andreas Müller <schnitzeltony@gmail.com>

RUN yum install -y dnf

RUN dnf -y update && dnf -y install \
    qt-devel \
    qt-creator \
    xauth \
    gtk2 \
    xterm \
    make \
    cmake \
    font-* \
    git \
    \
    && dnf clean all \
    && rpm -qa --queryformat '%10{size} - %-25{name} \t %{version}\n' | sort -n

