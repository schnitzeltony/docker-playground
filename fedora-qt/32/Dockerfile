# Container for qt5 CI
#
# to build/push change in this directory and enter
# docker build --tag fedora-qt5:32 .
# docker login docker.io
# docker push fedora-qt5:32 schnitzeltony/fedora-qt5:32

FROM fedora:32

MAINTAINER Andreas Müller <schnitzeltony@gmail.com>

RUN dnf -y --setopt=install_weak_deps=False --best update
RUN dnf -y --setopt=install_weak_deps=False --best install \
    findutils which \
    autoconf automake libtool \
    cmake git clazy \
    systemd-devel \
    openssl-devel \
    python3-devel python3-numpy \
    python3-pip \
    xsd xerces-c-devel \
    fftw-devel \
    php-jsonlint python3-jsonschema \
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
    qt5-qtconnectivity-devel \
    qt-devel \
    \
    kf5-networkmanager-qt-devel kf5-modemmanager-qt-devel kf5-syntax-highlighting-devel \
    \
    qwt-qt5-devel \
    \
    flatbuffers-devel protobuf-devel protobuf-compiler \
    \
    gtest-devel \
    xorg-x11-server-Xvfb \
    ghdl \
    npm \
    java \
    xz \
    ninja-build \
    xmlstarlet

RUN git clone https://github.com/schnitzeltony/cpputest.git; \
    cd cpputest; \
    git checkout fedora-patches; \
    mkdir cpputest_build; \
    cmake -DCMAKE_INSTALL_PREFIX=/usr -B cpputest_build; \
    cmake --build cpputest_build -j16; \
    cmake --install  cpputest_build;

RUN dnf clean all

RUN pip3 install vunit
RUN pip3 install vunit_hdl
RUN pip3 install colorama
# we ignored this :WARNING: Running pip install with root privileges is generally not a good idea.

RUN rpm -qa --queryformat '%10{size} - %-25{name} \t %{version}\n' | sort -n

