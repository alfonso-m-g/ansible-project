# Build and deploy remote target
```
docker build -t target1 .
docker run -it -d -p 2222:22 -p 80:80 --privileged --name target2 target1 /usr/sbin/init
docker exec -it target1 /bin/bash
```