FROM alpine:3.13

RUN apk update && apk --no-cache add dnsmasq

WORKDIR /
ADD ./docker-dnsmasq /
RUN mv dnsmasq.conf /etc/dnsmasq.conf
RUN mv dnsmasq.d/omniedge.io.conf /etc/dnsmasq.d/

EXPOSE 53/tcp
EXPOSE 53/udp

ENTRYPOINT ["dnsmasq", "-k"]