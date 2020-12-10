# This image has working dotnet on it, but the proper Stack
# configuration in order for it to work with Spacelift is tricky.

ARG RELEASE_VERSION

FROM ${REPOSITORY_BASE_PATH}/pulumi-base-debian:${RELEASE_VERSION}

USER root
RUN apt-get install -y icu-devtools
USER spacelift
RUN wget https://dot.net/v1/dotnet-install.sh
RUN chmod 777 dotnet-install.sh
RUN ./dotnet-install.sh -c LTS
SHELL ["/bin/sh", "-c"]
ENV DOTNET_ROOT="/home/spacelift/.dotnet"
ENV PATH="$PATH:/home/spacelift/.dotnet"
ENV PATH="$PATH:./.pulumi/bin"
