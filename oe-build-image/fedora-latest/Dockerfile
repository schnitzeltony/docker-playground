# Image for zenux autobuilder
#
# to build/push change in this directory and enter
# docker build --build-arg UID=1002 --build-arg GID=1002 --tag oe-build-image:latest .
# docker login docker.io
# docker push oe-build-image:latest schnitzeltony/oe-build-image:latest


FROM schnitzeltony/fedora-qt5:32

## set up env
USER root
ARG UID=1000
ARG GID=1000
RUN useradd -ms /bin/bash builder
RUN mkhomedir_helper builder
## set up tools
RUN dnf install --setopt=tsflags='' -y man-db
RUN dnf install --setopt=tsflags='' -y diffstat
RUN dnf install --setopt=tsflags='' -y sqlite
RUN dnf install --setopt=tsflags='' -y jq
RUN dnf reinstall --setopt=tsflags='' -y git
RUN dnf reinstall --setopt=tsflags='' -y git-core-doc
RUN dnf reinstall --setopt=tsflags='' -y dnf
RUN dnf install --setopt=tsflags='' -y findutils
## bitbake expected tools
RUN dnf install --setopt=tsflags='' -y bzip2
RUN dnf install --setopt=tsflags='' -y chrpath
RUN dnf install --setopt=tsflags='' -y cpio
RUN dnf install --setopt=tsflags='' -y file
RUN dnf install --setopt=tsflags='' -y hostname
RUN dnf install --setopt=tsflags='' -y patch
RUN dnf install --setopt=tsflags='' -y rpcgen
RUN dnf install --setopt=tsflags='' -y wget
RUN dnf install --setopt=tsflags='' -y which
RUN dnf install --setopt=tsflags='' -y langpacks-en
RUN dnf install --setopt=tsflags='' -y perl-core
RUN dnf install --setopt=tsflags='' -y ftp
RUN dnf install --setopt=tsflags='' -y diffstat
RUN dnf install --setopt=tsflags='' -y diffutils

#debug usecase
RUN dnf install --setopt=tsflags='' -y iputils
RUN chmod 4711 /usr/bin/ping
RUN usermod -u $UID builder
RUN groupmod -g $GID builder
USER builder

RUN rpm -qa --queryformat '%10{size} - %-25{name} \t %{version}\n' | sort -n
