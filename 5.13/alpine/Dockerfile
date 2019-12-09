FROM alpine:latest

ENV QT_VERSION 5.13.2

RUN apk update \
    && apk add --virtual .build-essential \
        ca-certificates \
        gcc \
        g++ \
        binutils \
        make \
        wget \
        linux-headers \
        gperf \
        bison \
        flex \
        python \
        pkgconfig \
        llvm-dev \
        dbus-dev \
        eudev-dev \
        openssl-dev \
        zlib-dev \
        zstd-dev \
        libxkbcommon-dev \
        glib-dev \
        perl \
        clang-dev \
        icu-dev \
        pcre2-dev \
        tslib-dev \
    && wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub \
    && wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.30-r0/glibc-dev-2.30-r0.apk \
    && apk add glibc-dev-2.30-r0.apk \
    && mkdir -p /build \
    && cd /build \
    && wget https://download.qt.io/official_releases/qt/5.13/$QT_VERSION/single/qt-everywhere-src-$QT_VERSION.tar.xz -O qtsource.tar.xz \
    && tar vxJf qtsource.tar.xz \
    && cd qt-everywhere-src-$QT_VERSION \
    && ./configure \
        -opensource \
        -confirm-license \
        -release \
        -optimize-size \
        -shared \
        -openssl-linked \
        -nomake examples \
        -nomake tests \
        -skip qt3d \
        -skip qtactiveqt \
        -skip qtandroidextras \
        -skip qtcharts \
        -skip qtconnectivity \
        -skip qtdatavis3d \
        -skip qtdeclarative \
        -skip qtdoc \
        -skip qtgamepad \
        -skip qtgraphicaleffects \
        -skip qtimageformats \
        -skip qtlocation \
        -skip qtlottie \
        -skip qtmacextras \
        -skip qtmultimedia \
        -skip qtnetworkauth \
        -skip qtpurchasing \
        -skip qtquickcontrols \
        -skip qtquickcontrols2 \
        -skip qtremoteobjects \
        -skip qtscript \
        -skip qtscxml \
        -skip qtsensors \
        -skip qtserialbus \
        -skip qtserialport \
        -skip qtspeech \
        -skip qtsvg \
        -skip qttools \
        -skip qttranslations \
        -skip qtvirtualkeyboard \
        -skip qtwayland \
        -skip qtwebchannel \
        -skip qtwebengine \
        -skip qtwebglplugin \
        -skip qtwebsockets \
        -skip qtwebview \
        -skip qtwinextras \
        -skip qtx11extras \
        -skip qtxmlpatterns \
        -no-opengl \
        -no-gui \
        -no-widgets \
        -no-widgets \
        -no-accessibility \
        -no-freetype \
        -no-harfbuzz \
        -no-gif \
        -no-ico \
        -qt-zlib

RUN make -j4
