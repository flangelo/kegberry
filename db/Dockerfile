FROM mariadb:10.11

RUN apt-get update && apt-get install -y --no-install-recommends tzdata && rm -rf /var/lib/apt/lists/*

COPY init_tzdata.sh /docker-entrypoint-initdb.d/init_tzdata.sh
RUN chmod +x /docker-entrypoint-initdb.d/init_tzdata.sh
