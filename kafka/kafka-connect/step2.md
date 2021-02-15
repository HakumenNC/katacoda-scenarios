
Now, we can launch the environment using [`docker-compose`](https://docs.docker.com/compose/)

```
docker-compose --project-name kafka-connect-pgsql -f /usr/local/bin/kafka-connect.yml up -d
```{{execute}}

```
docker-compose --project-name kafka-connect-pgsql -f /usr/local/bin/kafka-connect.yml ps
```{{execute}}