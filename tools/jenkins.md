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

## 安裝可執行 Docker 的 Jenkins

> 參考網址 [Jenkins Docker](https://www.jenkins.io/doc/book/installing/docker/)

1. 建立 Bridge Network

```sh
docker network create jenkins
```

2.建立 Docker dind

```sh
docker run --name jenkins_docker --detach --privileged --network jenkins --network-alias docker --env DOCKER_TLS_CERTDIR=/certs --volume jenkins-docker-certs:/certs/client --volume jenkins-data:/var/jenkins_home --publish 2376:2376 docker:dind --storage-driver overlay2
```

3. 建立客製化 Jenkins Image

```dockerfile
FROM jenkins/jenkins:lts-jdk11
USER root
RUN apt-get update && apt-get install -y lsb-release
RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc https://download.docker.com/linux/debian/gpg
RUN echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.asc] https://download.docker.com/linux/debian $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list
RUN apt-get update && apt-get install -y docker-ce-cli
RUN jenkins-plugin-cli --plugins "blueocean docker-workflow"
```

4. 建立 Docker Image

```sh
docker build -t jenkins_image .
```

5. 建立 Docker Jenkins

```sh
docker run --name jenkins --restart=on-failure --detach --network jenkins --env DOCKER_HOST=tcp://docker:2376 --env DOCKER_CERT_PATH=/certs/client --env DOCKER_TLS_VERIFY=1 --publish 8080:8080 --publish 50000:50000 --volume jenkins-data:/var/jenkins_home --volume jenkins-docker-certs:/certs/client:ro jenkins_image
```

6. 尋找 Jenkins Container ID

```sh
docker ps
```

7. 獲取登入 token

> Jenkins initial setup is required. An admin user has been created and a password generated.
> Please use the following password to proceed to installation:  
> xxxxxxxxxxxxxxxxxxxx

```sh
docker logs container_id
```

8. 開啟瀏覽器 `http://localhost:8080/` 進行初始化設定

9. Jenkins 的預設語言為瀏覽器語言，到瀏覽器語言設定將想要的語言放到第一順位，即可調整 Jenkins 顯示語言
