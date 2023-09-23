ARG PG_MAJOR=15
FROM timescale/timescaledb:latest-pg${PG_MAJOR}-bitnami
ARG PG_MAJOR=15
USER 0

RUN set -ex \
    && apt-get update \
    && apt-get -y install \
            libssl-dev \
            gcc \
            make \
    && mkdir -p /build/ \
    && git clone https://github.com/pgaudit/pgaudit /build/pgaudit \
    \
    # Build current version \
    && cd /build/pgaudit && rm -fr build \
    && git checkout REL_${PG_MAJOR}_STABLE\
    && make install USE_PGXS=1 \
    && cd ~ \
    \
    && apt-get autoremove --purge -y \
            libssl-dev \
            gcc \
            make \
    && apt-get clean -y \
    && rm -rf \
        /build \
        "${HOME}/.cache" \
        /var/lib/apt/lists/* \
        /tmp/*               \
        /var/tmp/*

USER 1001
