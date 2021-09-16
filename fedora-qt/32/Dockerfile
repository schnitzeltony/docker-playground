# Container for qt5 CI
#
# to build/push change in this directory and enter
# docker build --tag fedora-qt5:32 .
# docker push fedora-qt5:32 schnitzeltony/fedora-qt5:32

FROM fedora:32

MAINTAINER Andreas Müller <schnitzeltony@gmail.com>

RUN dnf -y update && dnf -y install \
    cmake git clazy \
    systemd-devel \
    openssl-devel \
    python3-devel python3-numpy \
    xsd xerces-c-devel \
    qt5-linguist qt5-doctools qt5-qtscript \
    qt5-qtlocation-devel \
    qt5-qtcharts-devel \
    qt5-qtdeclarative-devel \
    qt5-qtlocation-devel \
    qt5-qtmultimedia-devel \
    qt5-qtquickcontrols2-devel \
    qt5-qtsensors-devel \
    qt5-qtserialport-devel \
    qt5-qtsvg-devel \
    qt5-qttools-devel \
    qt5-qtvirtualkeyboard-devel \
    qt5-qtwayland-devel \
    qt5-qtwebchannel-devel \
    qt5-qtwebengine-devel \
    qt5-qtwebkit-devel \
    qt5-qtx11extras-devel \
    qt5-qtxmlpatterns-devel \
    \
    kf5-networkmanager-qt-devel kf5-modemmanager-qt-devel kf5-syntax-highlighting-devel \
    \
    qwt-qt5-devel \
    \
    flatbuffers-devel protobuf-devel protobuf-compiler \
    \
    && dnf clean all \
    && rpm -qa --queryformat '%10{size} - %-25{name} \t %{version}\n' | sort -n

