**Remove <none>:<none> image**

```
docker rmi -f $(docker images -f "dangling=true" -q)
```
