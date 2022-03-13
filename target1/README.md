# Build and deploy remote target
```
docker build -t target1 .
docker run -it -d -P --name target1 target1
docker exec -it target1 /bin/bash
```