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


## Connect cassandra from local

```
$ export CQLSH_HOST=127.0.0.1
$ export CQLSH_PORT=9042
$ cqlsh
Connected to Test Cluster at 127.0.0.1:9042.
[cqlsh 5.0.1 | Cassandra 3.0.12 | CQL spec 3.4.0 | Native protocol v4]
Use HELP for help.
cqlsh>
```

