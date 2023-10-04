# Image for oe-dunfell builds
#
# to build/push change in this directory and enter
# docker build --tag oe-build-image:fedora-32 .
# docker login docker.io
# docker push oe-build-image:fedora-32 schnitzeltony/oe-build-image:fedora-32

FROM fedora:32

MAINTAINER Andreas Müller <schnitzeltony@gmail.com>

# setup-scripts
RUN dnf -y install \
    sqlite \
    jq \
    git \
    findutils

# tools bitbake expects
RUN dnf -y install \
    bzip2 \
    chrpath \
    cpio \
    diffstat \
    diffutils \
    file \
    hostname \
    patch \
    rpcgen \
    wget \
    which \
    langpacks-en \
    perl-core \
    shared-mime-info

# get our blobs
RUN dnf -y install \
    ftp

# menuconfig
RUN dnf -y install \
    xfce4-terminal \
    xauth \
    ncurses-devel

# debug tools
RUN dnf -y install \
    strace \
    iputils

# user-experience
RUN dnf -y install \
    bash-completion

# openapi-generator
RUN dnf -y install \
    java


RUN dnf -y clean all
RUN rpm -qa --queryformat '%10{size} - %-25{name} \t %{version}\n' | sort -n

