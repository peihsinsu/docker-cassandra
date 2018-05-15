# Cassandra Docker

## Start cassandra in docker command...

Start master

```
docker run --name some-cassandra -d cassandra:3.0.12
```

Start slave

```
docker run --name some-cassandra2 -d --link some-cassandra:cassandra cassandra:3.0.12
```

Connect with cqlsh

```
docker run -it --link some-cassandra:cassandra --rm cassandra sh -c 'exec cqlsh "$CASSANDRA_PORT_9042_TCP_ADDR"'
```


## Start cassandra use docker compose

Start master

```
docker-compose up -d cassandra
```

Check master started...

```
docker-compose logs -f
```

Start nodes

```
docker-compose up -d
```


