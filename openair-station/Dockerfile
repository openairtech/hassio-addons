ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

WORKDIR /

ARG BUILD_ARCH
ARG BUILD_VERSION
RUN export ARCH=$(echo ${BUILD_ARCH} | sed -r 's/arm(v7|hf)/arm/g') \
    && curl -Lso /usr/bin/openair-station \
        "https://github.com/openairtech/station/releases/download/v${BUILD_VERSION}/openair-station.${ARCH}" \
    && chmod a+x /usr/bin/openair-station

COPY rootfs /
