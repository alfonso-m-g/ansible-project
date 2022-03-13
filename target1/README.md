# Build and deploy remote target
```
docker build -t target .

docker run -it -d -p 2222:22 -p 8080:80 --privileged --name target1 target /usr/sbin/init
docker run -it -d -p 2223:22 -p 8081:80 --privileged --name target2 target /usr/sbin/init

docker exec -it target1 /bin/bash
docker exec -it target2 /bin/bash
```