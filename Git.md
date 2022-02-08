# Git

- [Git](#git)
  - [git init](#git-init)
  - [git clone](#git-clone)
  - [git status](#git-status)
  - [git add](#git-add)
  - [git commit](#git-commit)
  - [git log](#git-log)
  - [git fetch](#git-fetch)
  - [git pull](#git-pull)
  - [git push](#git-push)
  - [git remote](#git-remote)
  - [git checkout](#git-checkout)
  - [git config](#git-config)

## git init

- `git init` 初始化數據庫(repository)

## git clone

- `git clone` 下載遠端數據庫

## git status

- `git status` 查詢目前 git 狀態

## git add

- `git add .` 將所有檔案加入到索引

## git commit

- `git commit -m "commit_message"` 將索引提交更新

## git log

- `git log` 查詢 commit 歷史紀錄

## git fetch

單純下載未合併

- `git fetch repository branch`更新本地數據庫

## git pull

> git fetch + git merge

下載並合併

- `git pull repository branch` 更新本地數據庫

## git push

- `git push repository branch` 更新遠端數據庫
- `git push repository branch -u` 加入`-u`可記住遠端數據庫名稱，設定為預設，之後可直接`git push`

## git remote

- `git remote` 查看遠端數據庫列表
- `git remote -v` 查看遠端數據庫列表，含 url
- `git remote add origin url` 註冊遠端數據庫

## git checkout

- `git checkout brnach_name` 切換到目標分支
- `git checkout sha-1` 切換到目標 commit

## git config

- `git config --list` 查詢 git 設定列表
- `git config --global user.name "user_name"` 設定使用者姓名
- `git config --global user.email "user_email"` 設定使用者 Email
