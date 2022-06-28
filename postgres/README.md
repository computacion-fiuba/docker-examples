1. Run postgres image
```
docker run --name postgresql -p 5432:5432 -e POSTGRES_PASSWORD=secret -d postgres:14.2
```

2. Go inside the image
```
docker exec -it postgresql psql -d postgres -U postgres
```

3. Add volume to postgres
```
docker run --name postgresql \
    -p 5432:5432 \
    -e POSTGRES_PASSWORD=secret \
    -v ${PWD}/postgres-data:/var/lib/postgresql/data \
    -d postgres:14.2
```

4. Add PgAdmin (https://hub.docker.com/r/fenglc/pgadmin4)
```
docker network create pg

docker run --name postgresql \
    -p 5432:5432 \
    -e POSTGRES_PASSWORD=secret \
    -v ${PWD}/postgres-data:/var/lib/postgresql/data \
    --network=pg \
    -d postgres:14.2

docker run --name pgadmin \
    -p 5050:5050 \
    --network=pg \
    --platform linux/x86_64 \
    -d fenglc/pgadmin4
```
