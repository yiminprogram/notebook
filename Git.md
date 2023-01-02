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
  - [git rebase](#git-rebase)
  - [git cherry-pick](#git-cherry-pick)
  - [git reset](#git-reset)
  - [git reflog](#git-reflog)
  - [git clean](#git-clean)
  - [git config](#git-config)
  - [git stash](#git-stash)

## git init

- `git init` 初始化數據庫(repository)

## git clone

- `git clone url` 下載遠端數據庫

## git status

- `git status` 查詢目前 git 狀態

## git add

- `git add .` 將所有檔案加入到索引
- `git add file_name` 將特定檔案加入至索引
- `git add *.html` 將所有 html 之檔案加入至索引

## git commit

- `git commit` 將索引中所有檔案提交更新(會進入預設編輯器中編輯 commit 訊息)
- `git commit -m "commit_message"` 將索引中所有檔案提交更新
- `git commit -a -m "commit message"` 略過`git add`直接將索引中檔案提交更新

## git log

- `git log` 查詢 commit 歷史紀錄
- `git log -3` 查詢前三筆資料
- `git log --oneline --graph` 查看線圖
- `git log --author="name"` 篩選特定作者名稱
- `git log --author="name1\|name2"` 篩選特定作者名稱(複數)
- `git log --grep="commit message"` 篩選特定 commit 訊息
- `git log -S "file_name"` 篩選特定檔案
- `git log --since="9am" --untile="12am"` 列出今日特定時間歷史訊息
- `git log --since="9am" --untile="12am" --after="2021-06"` 列出特定日期後時間內歷史資料

## git fetch

### 單純下載未合併

- `git fetch repository_name branch_name`更新本地數據庫

## git pull

> git fetch + git merge

### 下載並合併

- `git pull repository_name branch_name` 更新本地數據庫

## git push

- `git push repository_name branch_name` 更新遠端數據庫
- `git push repository_name branch_name -u` 加入`-u`可記住遠端數據庫名稱，設定為預設，之後可直接`git push`

## git remote

- `git remote` 查看遠端數據庫列表
- `git remote -v` 查看遠端數據庫列表，含 url
- `git remote add repository_name url` 註冊遠端數據庫

## git branch

- `git branch` 查看分支列表
- `git branch branch_name` 建立分支
- `git branch -d branch_name` 刪除分支
- `git branch -D branch_name` 強制刪除分支
- `git branch branch_name sha-1` 特定 commit 上建立分支

## git checkout

- `git checkout brnach_name` 切換到目標分支
- `git checkout sha-1` 切換到目標 commit
- `git checkout file_name` 還原工作目錄上已更改之檔案
- `git checkout <commit> -- <file-path` restore commit file

## git merge

- `git merge branch_name` 與目標分支合併
- `git merge branch_name --no-ff` 與目標分支合併，取消快轉機制
- `git merge --abort` 取消合併衝突狀態

## git rebase

- `git rebase branch_name` 目前分支複製合併至目標分支

## git cherry-pick

- `git cherry-pick sha-1 sha-1` 依序複製特定 commit 合併至目前分支

## git reset

- `git reset HEAD`全部加入索引的檔案還原到工作目錄
- `git reset HEAD file_name`單一檔案從索引還原到工作目錄
- `git reset HEAD^`還原前一個版本
- `git reset HEAD^ --mixed`還原前一個版本，檔案丟回工作目錄，預設 mixed，沒有加--mixed 也可以
- `git reset HEAD^ --hard` 還原前一個版本，檔案全部放棄刪除
- `git reset HEAD^ --soft` 還原前一個版本，檔案丟回索引
- `git reset sha-1` 還原到特定 commit
- `git reset -hard ORIG_HEAD` 還原合併前狀態

## git reflog

- `git reflog` 查看詳細歷史紀錄，包含刪除的所有記錄

## git clean

- `git clean -f` 刪除在工作目錄未加入索引的所有檔案

## git config

- `git config --list` show git configuration
- `git config --global user.name "user_name"` set git user name (global)
- `git config --global user.email "user_email"` set git user email (global)
- `git config --local user.name "user_name"` set git user name (local)
- `git config --local user.email "user_email"` set git user email (local)
- `git config --global core.editor "code --wait"` 設定使用 vscode 編輯 commit 訊息
- `git config --global alias.st status` 別名設定(git status 轉換成 git st)

## git stash

- `git stash` 將所有已列入追蹤的檔案建立暫存版本
- `git stash save` 將所有已列入追蹤的檔案建立暫存版本，save 參數可忽略，結果相同
- `git stash -u` 將所有已追蹤和未追蹤的檔案建立暫存版本
- `git stash pop` reset stash

## git diff

- `git diff` compare with last version
- `git diff <commit> --name-only` compare with commit version only file name
- `git diff <commit>` compare with commit version
- `git diff <commit1> <commit2>` compare commit1 with commit2
