# Docker

## 常用指令

- 查詢

```sh
# 查詢container
docker ps

# 查詢image
docker images
```

- 進入 bash

```sh
# 創建一個新的container
docker run -it <container_id> /bin/bash

# 進入指定的container
docker exec -it <container_id> /bin/bash
```
