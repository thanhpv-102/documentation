##### Remove none:none image

```
docker rmi -f $(docker images -f "dangling=true" -q)
```

##### Delete 'dangling' volumes

```
docker volume rm $(docker volume ls -qf dangling=true)
```

##### Self-Signed Registry With Access Restriction

1. Generate a self-signed certificate on our registry host

```
mkdir certs

openssl req -newkey rsa:4096 -nodes -sha256 -keyout certs/domain.key -x509 -days 356 -out certs/domain.crt
```
2. 
