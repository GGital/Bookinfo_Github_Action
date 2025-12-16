# Ratings Service

## License

MIT License

## How to run with docker

```bash
docker run -d --name mongodb -p 27017:27017 \
    -v $(pwd)/databases:/docker-entrypoint-initdb.d bitnami/mongodb
docker run -d --name ratings -p 8080:8080 --link mongodb:mongodb \
    -e SERVICE_VERSION=v2 -e 'MONGO_DB_URL=mongodb://mongodb:27017/ratings' ratings
```
