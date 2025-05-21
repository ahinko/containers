# renovate: datasource=docker depName=ghcr.io/cloudnative-pg/postgresql
ARG CNPG_TAG="17.5-1"

FROM ghcr.io/cloudnative-pg/postgresql:$CNPG_TAG

ARG CNPG_TAG
ARG POSTGRES_VERSION=${CNPG_TAG%.*}

# renovate: datasource=github-releases depName=tensorchord/VectorChord
ARG VECTORCHORD_TAG="0.3.0"

# To install any package we need to be root
USER root

# Install any extensions that we want
ADD https://github.com/tensorchord/VectorChord/releases/download/${VECTORCHORD_TAG}/postgresql-${POSTGRES_VERSION}-vchord_${VECTORCHORD_TAG}-1_amd64.deb ./vchord.deb

# Copy extensions from previous stage, install, then remove
RUN apt-get install -y --no-install-recommends ./vchord.deb && \
  rm -rf /download

# Change to the uid of postgres (26)
USER 26
