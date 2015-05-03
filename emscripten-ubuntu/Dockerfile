FROM ubuntu:14.04

MAINTAINER samhrussell

RUN apt-get update
RUN apt-get install -y python2.7
RUN apt-get install -y nodejs
RUN apt-get install -y build-essential
RUN apt-get install -y cmake
RUN apt-get install -y git-core
RUN apt-get install -y default-jre
RUN apt-get install -y wget
RUN apt-get install -y autoconf
RUN apt-get install -y automake
RUN apt-get install -y m4
RUN apt-get install -y libtool

RUN wget https://s3.amazonaws.com/mozilla-games/emscripten/releases/emsdk-portable.tar.gz

RUN tar -xzf emsdk-portable.tar.gz

WORKDIR emsdk_portable

RUN ./emsdk update

RUN ./emsdk install latest

RUN ./emsdk activate latest

# fix nodejs for ubuntu

RUN sed -i.bak s/\'node\'/\'nodejs\'/g ~/.emscripten

RUN /emsdk_portable/emscripten/master/emcc -v

