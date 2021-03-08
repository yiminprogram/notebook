# Mac 執行 MSSQL

## 1. 安裝 Docker

> 記憶體建議調成４ GB

## 2. 安裝 Azure Data Studio

## 3. 安裝 SQL SERVER (2019,2017) 容器映像檔

```bash
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Password' --name mssql -p 1433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
```

更改密碼

> 密碼應遵循 SQL Server 預設密碼原則，否則容器將無法設定 SQL Server 並停止運作。 根據預設，密碼的長度至少必須是 8 個字元，包含下列四種集合的其中三種字元：大寫字母、小寫字母、以 10 為底數的數字，以及符號。

```bash
SA_PASSWORD=Password
```

更改容器名稱

```bash
--name mssql
```

## 4. 檢視 Docker 狀態

```bash
docker ps //查看執行中的容器

docker ps -a //查看所有容器
```

## 5. 連接 SQL SERVER

```bash
docker exec -it <container_id|container_name> /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P <your_password>
```

> 可由 Docker Dashboard or GUI Tool 操作

## 6. 設定 Azure Data Studio 連接參數

- server -> localhost

- user name -> sa

- password -> 設定之密碼

## 7. 下載 AdventureWorks 範例資料庫

## 8. 匯入資料庫

terminal 移動至下載資料夾
先創建存放資料庫之資料夾

```bash
docker exec -it <container_name> mkdir /var/opt/mssql/backup
```

移動資料庫

```bash
docker cp <database_filename> <container_name>:/var/opt/mssql/backup
```

1. 開啟 Azure Data Studio

2. Restore

3. Restore from -> Backup file

4. Backup file path -> 選取新增 Backup 資料中存入之資料庫

5. Restore
