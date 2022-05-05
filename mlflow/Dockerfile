ARG MLFLOW_VERSION

FROM python:3.10-alpine

RUN pip install mlflow[extras]==${MLFLOW_VERSION} psycopg2

RUN useradd -u 65534 -g 65534

ENTRYPOINT [ "mlflow", "server" ]