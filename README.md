# Setting up NGINX Docker Reverse Proxy using docker compose

## Set up SSL certificates for domain

```bash
cd proxy/ssl

# Generate for webservice 1
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout site1.key -out site1.crt

# Generate for webservice 2
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout site2.key -out site2.crt
```

## Update local hostnames and IP addresses

Edit file /etc/hosts, add the contents below or similar

```
# Added for local sites on docker compose
127.0.0.1       site1.local
127.0.0.1       site2.local
# End of section
```

## Run applications

```bash
docker compose up
```

## Resources

- [How to set up NGINX Docker Reverse Proxy?](https://dev.to/sukhbirsekhon/what-is-docker-reverse-proxy-45mm)
- [SSL Configuration Generator](https://ssl-config.mozilla.org/#server=nginx)