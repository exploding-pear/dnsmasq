FROM ubuntu:jammy AS builder
ARG VERSION=2.86
WORKDIR /home/dnsmasq
RUN apt-get -y update && apt-get -y install curl make gcc
RUN curl -o dnsmasq-${VERSION}.tar.gz https://thekelleys.org.uk/dnsmasq/dnsmasq-${VERSION}.tar.gz && \
 tar -xvf dnsmasq-${VERSION}.tar.gz
WORKDIR /home/dnsmasq/dnsmasq-${VERSION}
RUN make install && apt-get remove -y curl make gcc && apt-get autoremove -y

ENTRYPOINT [ "dnsmasq" ]
CMD ["-d"]