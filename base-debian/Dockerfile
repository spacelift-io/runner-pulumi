FROM debian:latest
ARG PULUMI_VERSION

RUN echo "hosts: files dns" > /etc/nsswitch.conf \
  && adduser --disabled-password --uid=1983 spacelift

USER root
WORKDIR /home/spacelift
RUN apt-get update -y
RUN apt-get install -y wget
RUN wget "https://get.pulumi.com/releases/sdk/pulumi-${PULUMI_VERSION}-linux-x64.tar.gz"
RUN tar -xf pulumi-${PULUMI_VERSION}-linux-x64.tar.gz
RUN mv pulumi/* /usr/local/bin/
USER spacelift
