ARG RELEASE_VERSION
ARG REPOSITORY_BASE_PATH

FROM ${REPOSITORY_BASE_PATH}/runner-pulumi-base-debian:${RELEASE_VERSION}

USER root
RUN apt-get install -y icu-devtools
USER spacelift
RUN wget https://dot.net/v1/dotnet-install.sh
RUN chmod 777 dotnet-install.sh
RUN ./dotnet-install.sh -c Current
SHELL ["/bin/sh", "-c"]
ENV DOTNET_ROOT="/home/spacelift/.dotnet"
ENV PATH="$PATH:/home/spacelift/.dotnet"
ENV PATH="$PATH:./.pulumi/bin"
