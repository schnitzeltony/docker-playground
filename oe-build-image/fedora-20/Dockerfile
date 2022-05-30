# Image for qt4 qt-creator
#
# to build/push change in this directory and enter
# docker build --tag oe-build-image:fedora-20 .
# docker login docker.io
# docker push oe-build-image:fedora-20 schnitzeltony/oe-build-image:fedora-20

FROM docker.io/fedora:20

MAINTAINER Andreas Müller <schnitzeltony@gmail.com>

RUN yum install -y dnf

RUN dnf -y install \
    qt-devel \
    qt-creator \
    qt-mobility-devel \
    adobe-source-code-pro-fonts \
    xauth \
    gtk2 \
    xterm \
    make \
    cmake \
    font-* \
    git \
    gdb \
    \
    && dnf clean all \
    && rpm -qa --queryformat '%10{size} - %-25{name} \t %{version}\n' | sort -n

ENTRYPOINT ["/bin/bash"]
