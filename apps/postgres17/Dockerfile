# renovate: datasource=docker depName=ghcr.io/cloudnative-pg/postgresql
ARG CNPG_TAG="17.5-19"

FROM ghcr.io/cloudnative-pg/postgresql:$CNPG_TAG-bookworm

ARG CNPG_TAG
ARG POSTGRES_VERSION=${CNPG_TAG%.*}

# renovate: datasource=github-releases depName=tensorchord/VectorChord
ARG VECTORCHORD_TAG="0.4.3"

# To install any package we need to be root
USER root
ADD https://github.com/tensorchord/VectorChord/releases/download/${VECTORCHORD_TAG}/postgresql-${POSTGRES_VERSION}-vchord_${VECTORCHORD_TAG}-1_amd64.deb /tmp/vchord.deb
RUN apt-get install -y /tmp/vchord.deb && rm -f /tmp/vchord.deb

# Change to the uid of postgres (26)
USER postgres
