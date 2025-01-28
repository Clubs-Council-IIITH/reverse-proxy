# Reverse Proxy

##  Setup
Create a new external Docker network named `reverse_proxy` (if it doesn't exist):
```
docker network create reverse_proxy --subnet 172.19.0.0/16 --gateway 172.19.0.1
```

Copy .env file and set appropriate default email ID:
```
cp .env.example .env
```

Start all services:
```
docker compose up -d
```

## Example compose config for sites
```
version: '3.8'

networks:
  reverse_proxy:
    external: true

services:
  nginx:
    image: nginx:1.23-alpine
    volumes:
      - ./public_html:/usr/share/nginx/html:ro
    expose:
      - 80
    environment:
      - VIRTUAL_HOST=subdomain.domain.com
      - LETSENCRYPT_HOST=subdomain.domain.com
    networks:
      - reverse_proxy
```
