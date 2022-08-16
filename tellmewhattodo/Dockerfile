ARG FROM_IMAGE=python
ARG FROM_IMAGE_TAG=3.10-slim-bullseye
FROM ${FROM_IMAGE}:${FROM_IMAGE_TAG}

ARG APP_VERSION=2.1.0
RUN pip install \
    --no-cache-dir \
    --quiet \
    "tellmewhattodo==${APP_VERSION}"


# Not good practice to be root
WORKDIR /tellme
RUN mkdir -p .whattodo/ && chown -R 1000:1000 .whattodo/
USER 1000

ENTRYPOINT [ "tellmewhattodo" ]