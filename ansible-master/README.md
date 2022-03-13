# Build and deploy ansible master node
```
docker build -t ansible-master .
docker run -it -d -P --name ansible-master ansible-master
docker exec -it ansible-master /bin/bash
```