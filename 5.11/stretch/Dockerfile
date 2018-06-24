FROM buildpack-deps:stretch

ENV QT_VERSION 5.11.1

RUN mkdir -p /build \
    && cd /build \
    && wget https://download.qt.io/official_releases/qt/5.11/5.11.1/single/qt-everywhere-src-5.11.1.tar.xz -O qtsource.tar.xz \
    && tar vxJf qtsource.tar.xz \
    && echo "finish"
    && cd qt-everywhere-src-5.11.1 \
    && ./configure -opensource -confirm-license -release -optimize-size
