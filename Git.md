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
  - [git branch](#git-branch)
  - [git checkout](#git-checkout)
  - [git merge](#git-merge)
  - [git reset](#git-reset)
  - [git reflog](#git-reflog)
  - [git clean](#git-clean)
  - [git config](#git-config)

## git init

- `git init` 初始化數據庫(repository)

## git clone

- `git clone url` 下載遠端數據庫

## git status

- `git status` 查詢目前 git 狀態

## git add

- `git add .` 將所有檔案加入到索引

## git commit

- `git commit -m "commit_message"` 將索引提交更新

## git log

- `git log` 查詢 commit 歷史紀錄
- `git log --oneline --graph` 查看線圖

## git fetch

單純下載未合併

- `git fetch repository_name branch_name`更新本地數據庫

## git pull

> git fetch + git merge

下載並合併

- `git pull repository_name branch_name` 更新本地數據庫

## git push

- `git push repository_name branch_name` 更新遠端數據庫
- `git push repository_name branch_name -u` 加入`-u`可記住遠端數據庫名稱，設定為預設，之後可直接`git push`

## git remote

- `git remote` 查看遠端數據庫列表
- `git remote -v` 查看遠端數據庫列表，含 url
- `git remote add repository_name url` 註冊遠端數據庫

## git branch

- `git branch`查看分支列表
- `git branch branch_name` 建立分支
- `git branch -d branch_name`刪除分支
- `git branch -D branch_name`強制刪除分支
- `git branch branch_name sha-1`特定 commit 上建立分支

## git checkout

- `git checkout brnach_name` 切換到目標分支
- `git checkout sha-1` 切換到目標 commit
- `git checkout file_name`還原工作目錄上已更改之檔案

## git merge

- `git merge branch_name` 與目標分支合併
- `git merge branch_name --no-ff` 與目標分支合併，取消快轉機制
- `git merge --abort` 取消合併衝突狀態

## git reset

- `git reset HEAD`全部加入索引的檔案還原到工作目錄
- `git reset HEAD file_name`單一檔案從索引還原到工作目錄
- `git reset HEAD^`還原前一個版本
- `git reset HEAD^ --mixed`還原前一個版本，檔案丟回工作目錄，預設 mixed，沒有加--mixed 也可以
- `git reset HEAD^ --hard`還原前一個版本，檔案全部放棄刪除
- `git reset HEAD^ --soft`還原前一個版本，檔案丟回索引
- `git reset sha-1`還原到特定 commit
- `git reset -hard ORIG_HEAD`還原合併前狀態

## git reflog

- `git reflog`查看詳細歷史紀錄，包含刪除的所有記錄

## git clean

- `git clean -f`刪除在工作目錄未加入索引的所有檔案

## git config

- `git config --list` 查詢 git 設定列表
- `git config --global user.name "user_name"` 設定使用者姓名
- `git config --global user.email "user_email"` 設定使用者 Email
- `git config --global core.editor "code --wait"`設定使用 vscode 編輯 commit 訊息
