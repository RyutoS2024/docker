## 停止中のコンテナも含めて表示する

```
docker container ls -a
```

## 停止中のコンテナを起動する

```
docker start CONTINER_ID
```

## 起動したコンテナの中に入る

```
docker exec -it CONTAINER_ID /bin/bash
```

