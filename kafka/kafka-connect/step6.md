> Optional, only for live transfer viewing

```
docker run -it --net=host --rm --name kafka-json-producer confluentinc/cp-schema-registry:6.0.1 bash
```{{execute T2}}

```
kafka-json-schema-console-producer \
    --broker-list localhost:9092 \
    --topic demo.json.sms \
    --property schema.registry.url=http://localhost:8081 \
    --property value.schema='{"type":"object","properties":{"phoneNumberEmitter":{"type":"string"},"phoneNumberReceiver":{"type":"string"},"message":{"type":"string"}},"additionalProperties":false}'
```{{execute T2}}

## Produce messages

```
{"phoneNumberEmitter":"123546","phoneNumberReceiver":"321654","message":"Testing is easier than debugging"}
{"phoneNumberEmitter":"654987","phoneNumberReceiver":"789456","message":"A clever person solves a problem. A wise person avoids it"}
{"phoneNumberEmitter":"112233","phoneNumberReceiver":"445566","message":"Real programmers don't comment their code. If it was hard to write, it should be hard to understand"}
{"phoneNumberEmitter":"665544","phoneNumberReceiver":"998877","message":"Talk is cheap. Show me the code"}
{"phoneNumberEmitter":"789987","phoneNumberReceiver":"456654","message":"The computer was born to solve problems that did not exist before"}
```{{execute T2}}

Stop producing messages and exit the container
