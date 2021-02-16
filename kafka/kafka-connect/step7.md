See some differents issues.

## Malformed message

```
docker run -it --net=host --rm --name kafka-json-producer confluentinc/cp-schema-registry:6.0.1 bash
```{{execute T1}}

```
kafka-json-schema-console-producer \
    --broker-list localhost:9092 \
    --topic demo.json.sms \
    --property schema.registry.url=http://localhost:8081 \
```{{execute T1}}

```
{"phoneNumberEmitter":"123546","phoneNumberReceiver":"321654","text":"oh no, this is a wrong structure"}
```{{execute T1}}