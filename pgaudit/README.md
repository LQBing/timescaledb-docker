# postgresql-docker

timescaledb docker image with [timescale/timescaledb:latest-pg${PG_MAJOR}](https://github.com/timescale/timescaledb-docker/blob/main/Dockerfile) & [pgaudit](https://github.com/pgaudit/pgaudit)

pull [image](https://hub.docker.com/r/lqbing/timescaledb)

```shell
docker pull lqbing/timescaledb:pg15-pgaudit
```

build

```shell
docker build --build-arg PG_MAJOR=15 -t lqbing/timescaledb:pg15-pgaudit .
```
