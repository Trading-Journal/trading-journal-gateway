# Trading Journal Gateway

## Change Log

### 2.0.0
* Spring 3.1.0
* Native Image with Build packs

### 1.1.1
* Add CORS configuration

### 1.1.0
* Fully functional gateway for trading journal entry

### 1.0.0
* Fully functional gateway for trading journal authentication

## Running

### Locally

Set the active profile as local:

```bash
-Dspring.active.profiles=local
```
## Docker

### Build for deployment


```.\mvnw  spring-boot:build-image -Pnative```

Tag your image to latest: ```docker tag allanweber/trading-journal-gateway:<VERSION> allanweber/trading-journal-gateway:latest``` 

Push image to registry: ```docker push allanweber/trading-journal-gateway:latest```

### Run it with env variables

* Get postgres container ip: ```docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' CONTAINER_ID```

```bash
docker run -p 8888:8888 --name trading-journal-gateway allanweber/trading-journal-gateway:<VERSION>
```