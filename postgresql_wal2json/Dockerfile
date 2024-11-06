FROM ghcr.io/railwayapp-templates/postgres-ssl:16
# Use Railways Default SSL Postgres Template

RUN apt-get update
RUN apt-get install -y postgresql-16-wal2json
CMD ["postgres", "-c", "wal_level=logical"]
# Install and add wal2json. This is used & required by Meilisync
