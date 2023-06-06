# Trading Journal Gateway

## Change Log

### 1.1.0
Fully functional gateway for trading journal entry

### 1.0.0
Fully functional gateway for trading journal authentication

## Running

### Locally

Set the active profile as local:

```bash
-Dspring.active.profiles=local
```
## Docker

### Build for deployment

For this option, you must provide your own private and public keys, add it to the image and configure the proper environment variables to read those files

```docker build -t allanweber/trading-journal-gateway:1.0.0 -f docker/Dockerfile .```

Tag your image to latest: ```docker tag allanweber/trading-journal-gateway:1.0.0 allanweber/trading-journal-gateway:latest``` 

Push image to registry: ```docker push allanweber/trading-journal-gateway:latest```

### Run it with env variables

* Get postgres container ip: ```docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' CONTAINER_ID```

```bash
docker run -p 8888:8888 --name trading-journal-gateway allanweber/trading-journal-gateway:VERSION
```