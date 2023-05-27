# Jenkins

## 安裝一般 Jenkins

1. 安裝 Docker
2. Docker Hub 搜尋 [Jenkins](https://hub.docker.com/r/jenkins/jenkins)
3. [GitHub - Official Jenkins Docker image](https://github.com/jenkinsci/docker/blob/master/README.md)
4. docker 啟用容器，執行 Jenkins image

```sh
docker run -d -v jenkins_home:/var/jenkins_home -p 8080:8080 -p 50000:50000 --restart=on-failure jenkins/jenkins:lts-jdk11
```

- `-d` 背景執行
- `-v jenkins_home:/var/jenkins_home` 創建 volumn(jenkins_home)mapping 到 container 裡面(/var/jenkins_home)，使用 volumn 目的為重啟 container Jenkins 設定會持續存在
- `-p` port mapping

5. 尋找 Jenkins Container ID

```sh
docker ps
```

6. 獲取登入 token

> Jenkins initial setup is required. An admin user has been created and a password generated.
> Please use the following password to proceed to installation:  
> xxxxxxxxxxxxxxxxxxxx

```sh
docker logs container_id
```

6. 開啟瀏覽器 `http://localhost:8080/` 進行初始化設定
7. Jenkins 的預設語言為瀏覽器語言，到瀏覽器語言設定將想要的語言放到第一順位，即可調整 Jenkins 顯示語言
