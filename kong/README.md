# kong

This folder contains the docker-compose.yml file to get Kong inside Docker up.

## How to use

Add an appropriate .env file containing override values compared to those present in the docker-compose.yml file.

Read the instructions in parent [readme](../README.md#usage) on how to run `docker compose` commands.

## Initial setup

There are some initial configurations to consider, so go read the [setup/README.md](./setup/README.md) instructions.

## Note

Access logging in Kong is set to `/dev/null` due to the incredible amount of requests to the TibiaData API.
