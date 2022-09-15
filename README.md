# Reverse Proxy

##  Setup
Create a new external Docker network named `reverse_proxy` (if it doesn't exist):
```
docker network create reverse_proxy
```

Copy .env file and set appropriate default email ID:
```
cp .env.example .env
```

Start all services:
```
docker compose up -d
```
