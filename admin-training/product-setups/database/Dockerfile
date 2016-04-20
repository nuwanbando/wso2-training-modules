FROM mysql

COPY artifacts/apimdb.sql /docker-entrypoint-initdb.d/
COPY artifacts/userdb.sql /docker-entrypoint-initdb.d/
COPY artifacts/regdb.sql /docker-entrypoint-initdb.d/
COPY artifacts/analytics.sql /docker-entrypoint-initdb.d/

EXPOSE 3306