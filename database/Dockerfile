FROM postgres:17.2-alpine

ENV POSTGRES_DB=db \
    POSTGRES_USER=usr \
    POSTGRES_PASSWORD=pwd

COPY createScheme.sql /docker-entrypoint-initdb.d/01-create-schema.sql
COPY insertData.sql /docker-entrypoint-initdb.d/02-insert-data.sql