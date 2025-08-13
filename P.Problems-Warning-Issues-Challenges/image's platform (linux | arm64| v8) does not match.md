```sh
docker run python:3.9
WARNING: The requested image's platform (linux/arm64/v8) does not match the detected host platform (linux/amd64/v3) and no specific platform was requested
exec /usr/local/bin/python3: exec format error
```

```sh
uname -m
docker pull --platform linux/arm64/v8 python:3.9
docker inspect --format='{{.Architecture}}' python:3.9
docker inspect --format='{{.Architecture}}' nginx

```
