##### Install docker
```
curl -sL https://get.docker.com/ | sudo -E bash -
```

##### Remove none:none image

```
docker rmi -f $(docker images -f "dangling=true" -q)
```

##### Delete 'dangling' volumes

```
docker volume rm $(docker volume ls -qf dangling=true)
```

##### Remove docker logs
```
find /var/lib/docker/containers/ -type f -name "*.log" -delete
```
