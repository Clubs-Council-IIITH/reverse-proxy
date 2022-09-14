# Reverse Proxy

##  Setup
Create a new external Docker network named `reverse_proxy` (if it doesn't exist):
```
docker network create reverse_proxy
```

Start docker-gen service:
```
docker compose up -d
```
