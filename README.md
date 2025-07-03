Current development setup:

1- up nats: /launcher docker compose up --build
2- up sales db /data-ingestor-ms docker compose up --build
3- up forecast db /forecast-access-ms docker compose up --build
4- up auth mongo db /auth-ms docker compose up --build

if new mongo db:
```bash
docker exec -it mongo_auth_database mongosh
rs.initiate()
```
make sure there is no conflict with local mongodb

5- /data-ingestor-ms npm run start:dev
6- /forecast-access-ms npm run start:dev
7- /forecast-ms poetry run poe start
8- /auth-ms npm run start:dev
9- /client-ms npm run start:dev


If need to publish anything:

docker run --rm -it --network host synadia/nats-box

nats pub internal.sales.persisted "test message"

nats sub internal.forecast.generated


# Forecasting System

## Overview and Objectives

## Architecture

## Infrastructure

## Setup and Deployment
