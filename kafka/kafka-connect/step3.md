
Create the `postgresql-sms-sink.json` connector :

## Send configuration file

```
curl http://localhost:8083/connectors \
    -X POST \
    -H "Content-Type: application/json" \
    --data @/usr/local/bin/postgresql-sms-sink.json
```{{execute}}

## Connector status

Check connector's state :

```
curl -X GET http://localhost:8083/connectors/postgresql-sms-sink-connector/status | jq
```{{execute}}

> Kafka and the postgreSQL are now *linked*