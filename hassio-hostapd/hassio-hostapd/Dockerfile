ARG BUILD_FROM=ghcr.io/hassio-addons/base:16.3.6
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV LANG C.UTF-8

# Install requirements for add-on
RUN apk update && apk add --no-cache bash jq iw hostapd networkmanager net-tools sudo && rm -rf /var/cache/apk/*
RUN echo "intalled requirements"

COPY hostapd.conf /
COPY interfaces /etc/network/interfaces
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
