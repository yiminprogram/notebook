# Docker 指令

- ### 建立資料夾

```bash
docker exec -it <container_name> mkdir <folder_path>
```

- ### 複製檔案

```bash
docker cp <filename> <container_name>:<folder_path>
```

- ### 刪除檔案

```bash
docker exec -it <container_name> rm <file_path>
```
