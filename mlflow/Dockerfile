ARG FROM_IMAGE=python
ARG FROM_IMAGE_TAG=3.10-slim-bullseye
FROM ${FROM_IMAGE}:${FROM_IMAGE_TAG}}

ARG APP_VERSION=1.25.1
RUN pip install \
    --no-cache-dir \
    --quiet \
    "mlflow[extras]==${APP_VERSION}" \
    "psycopg2-binary>2.9,<3"

# Run as non-root user
WORKDIR /opt/mlflow
RUN chown 65534:0 /opt/mlflow
USER 65534

ENTRYPOINT [ "mlflow", "server" ]