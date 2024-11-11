FROM long2ice/meilisync

# Install gettext to use envsubst, if it’s not available in the base image
RUN apt-get update && apt-get install -y gettext

WORKDIR /meilisync

# Set ARGS ( See Railway documentaion about using vairables on railway )
ARG MEILISERCH_URL
ARG MEILISERCH_ADMIN_API_KEY
ARG POSTGRES_HOST
ARG POSTGRES_PORT
ARG POSTGRES_DB
ARG POSTGRES_USER
ARG POSTGRES_PASSWORD
ARG DEBUG
ARG TABLE_1
ARG INDEX_1
ARG PK_1

# Copy the config.yml template file from the host to the container
COPY ./config.yml /meilisync/config.yml.template

# Use CMD to preprocess config.yml using the variables and then run the default command
RUN envsubst < /meilisync/config.yml.template > /meilisync/config.yml
CMD ["meilisync", "start"]
