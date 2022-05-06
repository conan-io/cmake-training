FROM ubuntu:22.04

USER root

RUN apt-get -qq update \
    && apt-get -qq install -y --no-install-recommends \
       tree \
       graphviz \
       vim \
       nano \
       less \
       sudo \
       g++ \
       make \
       ninja-build \
       cmake

WORKDIR /labs