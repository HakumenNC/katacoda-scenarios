
In this step, we will produce messages according a specific structure :

```json
{
    "type": "object",
    "properties": {
        "phoneNumberEmitter": {
            "type": "string"
        },
        "phoneNumberReceiver": {
            "type": "string"
        },
        "message": {
            "type": "string"
        }
    }
}
```

## Create the producer

Run a `confluentinc/cp-schema-registry:5.5.0` container in [interactive mode](https://docs.docker.com/engine/reference/commandline/run/#assign-name-and-allocate-pseudo-tty---name--it)

```
docker run -it --net=host --rm --name kafka-json-producer confluentinc/cp-schema-registry:5.5.0 bash
```{{execute}}

```
kafka-json-schema-console-producer \
    --broker-list localhost:9092 \
    --topic demo.json.sms \
    --property schema.registry.url=http://localhost:8081 \
    --property value.schema='{"type":"object","properties":{"phoneNumberEmitter":{"type":"string"},"phoneNumberReceiver":{"type":"string"},"message":{"type":"string"}},"additionalProperties":false}'
```{{execute}}

## Produce message

```
{"phoneNumberEmitter":"112233","phoneNumberReceiver":"445566","message":"Don't worry, be happy"}
```{{execute}}

another data examples below :

```
{"phoneNumberEmitter":"332211","phoneNumberReceiver":"665544","message":"The last but not least"}
{"phoneNumberEmitter":"445566","phoneNumberReceiver":"778899","message":"You shall not pass"}
{"phoneNumberEmitter":"778899","phoneNumberReceiver":"665544","message":"It's dangerous to go alone"}
```{{execute}}