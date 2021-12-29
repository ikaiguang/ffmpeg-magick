FROM jrottenberg/ffmpeg:4.1-ubuntu as build

ADD https://download.imagemagick.org/ImageMagick/download/ImageMagick-7.1.0-19.tar.gz /build_image_magick/ImageMagick-7.1.0-19.tar.gz

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get install -yqq --no-install-recommends build-essential && \
    cd /build_image_magick && \
    tar -zxf ImageMagick-7.1.0-19.tar.gz && \
    cd ./ImageMagick-7.1.0-19 && \
    ./configure && \
    make && make install && \
    ldconfig /usr/local/lib && \
    cd / && rm -rf /build_image_magick && \
    apt-get autoremove -y && \
    apt-get clean -y
