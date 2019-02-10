FROM docker:18.09.1

ENV PACK_VERSION 0.0.9

RUN wget https://github.com/buildpack/pack/releases/download/v"$PACK_VERSION"/pack-"$PACK_VERSION"-linux.tar.gz
RUN tar xvf pack-"$PACK_VERSION"-linux.tar.gz -C /usr/local/bin
RUN rm pack-"$PACK_VERSION"-linux.tar.gz
CMD pack build $yourImageName