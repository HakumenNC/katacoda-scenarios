Data visualisations on differents steps.

## Topic

First, we consume the topic `demo.json.sms`...

```
docker run --net=host --rm wurstmeister/kafka:2.11-2.0.0 sh opt/kafka_2.11-2.0.0/bin/kafka-console-consumer.sh \
    --bootstrap-server localhost:9092 \
    --topic demo.json.sms \
    --from-beginning
```{{execute}}

## Database

... And the final destination in the postgreSQL database. Let's running a pgsql container

```
docker run --name postgres-psql -it --rm --network host postgres psql -h localhost -p 5433 -U user -d db
```{{execute}}

Fill the password

```
password
```{{execute}}

And ensure all messages are stored on sink database

```
select * from sms;
```{{execute}}