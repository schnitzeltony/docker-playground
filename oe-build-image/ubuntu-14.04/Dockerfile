# Image for very old oe-builds
#
# to build/push change in this directory and enter
# docker build --tag oe-build-image:ubuntu-14.04 .
# docker login docker.io
# docker push oe-build-image:ubuntu-14.04 schnitzeltony/oe-build-image:ubuntu-14.04

FROM ubuntu-debootstrap:14.04

MAINTAINER Andreas Müller <schnitzeltony@gmail.com>

## install tools needed setup-tool
RUN apt-get update -y
RUN apt-get install -y software-properties-common
RUN apt-get install -y build-essential
RUN apt-get install -y dialog apt-utils
RUN apt-get -y install manpages

# oe
RUN apt-get install -y man-db
RUN apt-get install -y git
RUN apt-get install -y git-man
RUN apt-get install -y gawk
RUN apt-get install -y diffstat
RUN apt-get install -y texinfo
RUN apt-get install -y chrpath
RUN apt-get install -y python2.7 python2.7-dev
RUN apt-get install -y wget
RUN apt-get install -y gettext
RUN apt-get install -y realpath
RUN apt-get install -y make
RUN apt-get install -y bzip2
RUN apt-get install -y cpio
RUN apt-get install -y ftp
RUN apt-get update -y
RUN apt-get install -y sed
RUN apt-get install -y jq
RUN apt-get install -y sqlite3
RUN apt install -y iputils-ping
RUN apt install -y xfce4-terminal
RUN apt install -y xauth
RUN apt install -y ncurses-dev

# More or less dirty hack to install new ssh client 
RUN apt-add-repository --y 'deb http://archive.ubuntu.com/ubuntu xenial main '
RUN apt-get update -y
RUN apt-get install -y openssh-client
RUN apt-add-repository --remove 'deb http://archive.ubuntu.com/ubuntu  xenial main '
RUN apt-get update -y


ENTRYPOINT ["/bin/bash"]

