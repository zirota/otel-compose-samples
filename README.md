# Docker Compose Samples

A bunch of docker compose samples mainly to test the compatibility with Opentelemetry

Opentelemetry data is sent to Elasticsearch APM for simplicity due to the support of types of telemetry data: traces, metrics and logs.

## Getting Started

Start by starting Elasticsearch, Kibana and the APM server.

### Setup ELK environments

```
cp elk/.env.sample elk/.env
```
Set your desired environment variables inside `.env`

### Start ELK
```
cd elk
docker-compose up -d
```
### Testing Services


Test out other services for example, trino:

Download the Opentelemetry Java Agent and place it in `trino/opt/opentelemetry`.

```
cd trino
docker-compose up -d
```

Head over to Kibana at http://localhost:5601 to view the telemetry data from APM.
