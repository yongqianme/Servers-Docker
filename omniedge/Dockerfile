FROM ubuntu:18.04

ARG ARCH=amd64
ARG VERSION=0.2.3

RUN apt-get update && \
  apt-get install -y  wget unzip \
  && wget https://github.com/omniedgeio/omniedge/releases/download/v${VERSION}/omniedgecli-${VERSION}-${ARCH}.zip
RUN unzip omniedgecli-${VERSION}-${ARCH}.zip -d /usr/sbin
RUN rm omniedgecli-${VERSION}-${ARCH}.zip

RUN chmod +x /usr/sbin/omniedge
RUN omniedge version

COPY entrypoint /usr/sbin/entrypoint
RUN chmod +x /usr/sbin/entrypoint

ENTRYPOINT ["/usr/sbin/entrypoint"]
