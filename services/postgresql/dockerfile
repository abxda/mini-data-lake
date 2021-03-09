FROM postgres

ADD /init/00_shared_create_user.sh /docker-entrypoint-initdb.d/
ADD /init/01_shared_create_db.sh /docker-entrypoint-initdb.d/
ADD /init/02_superset_create_user.sh /docker-entrypoint-initdb.d/
ADD /init/03_superset_create_db.sh /docker-entrypoint-initdb.d/
ADD /init/04_airflow_create_user.sh /docker-entrypoint-initdb.d/
ADD /init/05_airflow_create_db.sh /docker-entrypoint-initdb.d/

USER root

RUN chmod +x /docker-entrypoint-initdb.d/00_shared_create_user.sh
RUN chmod +x /docker-entrypoint-initdb.d/01_shared_create_db.sh
RUN chmod +x /docker-entrypoint-initdb.d/02_superset_create_user.sh
RUN chmod +x /docker-entrypoint-initdb.d/03_superset_create_db.sh
RUN chmod +x /docker-entrypoint-initdb.d/04_airflow_create_user.sh
RUN chmod +x /docker-entrypoint-initdb.d/05_airflow_create_db.sh