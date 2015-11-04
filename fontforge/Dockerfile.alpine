FROM alpine:3.2

ENV REFRESHED_AT 20151104

RUN apk --update add alpine-sdk xz poppler pango m4 libtool perl autoconf automake coreutils python-dev zlib-dev freetype-dev glib-dev

RUN git clone https://github.com/BWITS/fontforge.git

WORKDIR /fontforge
RUN ./bootstrap --force
RUN ./configure --without-iconv
RUN make
RUN make install
CMD ["/usr/local/bin/fontforge"]
