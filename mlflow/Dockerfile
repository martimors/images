ARG PYTHON_IMAGE_TAG=3.10-slim-bullseye
FROM python:${PYTHON_IMAGE_TAG}

ARG MLFLOW_VERSION=1.25.1
RUN pip install \
    --no-cache-dir \
    "mlflow[extras]==${MLFLOW_VERSION}" \
    "psycopg2-binary>2.9,<3"

# Run as non-root user
WORKDIR /opt/mlflow
RUN chown 65534:0 /opt/mlflow
USER 65534

ENTRYPOINT [ "mlflow", "server" ]