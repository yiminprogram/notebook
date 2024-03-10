# git command

## git init

```sh
# 初始化數據庫(repository)
git init
```

## git clone

```sh
# 下載遠端數據庫
git clone remote_url
```

## git status

```sh
# 查詢目前 git 狀態
git status
```

## git add

```sh
# 將所有檔案加入到索引
git add .

# 將特定檔案加入至索引
git add file_name

# 將所有 html 之檔案加入至索引
git add *.html
```

## git commit

```sh
# 將索引中所有檔案提交更新(會進入預設編輯器中編輯 commit 訊息)
git commit

# 將索引中所有檔案提交更新
git commit -m "commit_message"

# 略過git add直接將索引中檔案提交更新
git commit -a -m "commit message"

# 將這次改動提交到上一個 commit 中
git commit --amend
```

## git log

```sh
# 查詢 commit 歷史紀錄
git log

# 查詢前三筆資料
git log -3

# 查看線圖
git log --oneline --graph

# 篩選特定作者名稱
git log --author="name"

# 篩選特定作者名稱(複數)
git log --author="name1\|name2"

# 篩選特定 commit 訊息
git log --grep="commit message"

# 篩選特定檔案
git log -S "file_name"

# 列出今日特定時間歷史訊息
git log --since="9am" --untile="12am"

# 列出特定日期後時間內歷史資料
git log --since="9am" --untile="12am" --after="2021-06"
```

## git fetch

```sh
# 單純下載未合併
# 更新本地數據庫
git fetch repository_name branch_name
```

## git pull

```sh
# git fetch + git merge
# 下載並合併
# 更新本地數據庫
git pull repository_name branch_name
```

## git push

```sh
# 更新遠端數據庫
git push repository_name branch_name

# 加入-u可記住遠端數據庫名稱，設定為預設，之後可直接git push
git push repository_name branch_name -u
```

## git remote

```sh
# 查看遠端數據庫列表
git remote

# 查看遠端數據庫列表，含 url
git remote -v

# 註冊遠端數據庫
git remote add repository_name url
```

## git branch

```sh
# 查看分支列表
git branch

# 建立分支
git branch branch_name

# 刪除分支
git branch -d branch_name

# 強制刪除分支
git branch -D branch_name

# 特定 commit 上建立分支
git branch branch_name sha-1
```

## git checkout

```sh
# 切換到目標分支
git checkout brnach_name

# 切換到目標 commit
git checkout sha-1

# 還原工作目錄上已更改之檔案
git checkout file_name

# 恢復 commit 檔案
git checkout commit -- file_path
```

## git merge

```sh
# 與目標分支合併
git merge branch_name

# 與目標分支合併，取消快轉機制
git merge branch_name --no-ff

# 取消合併衝突狀態
git merge --abort
```

## git rebase

```sh
# 目前分支複製合併至目標分支
git rebase branch_name
```

## git cherry-pick

```sh
# 依序複製特定 commit 合併至目前分支
git cherry-pick sha-1 sha-1
```

## git reset

```sh
# 全部加入索引的檔案還原到工作目錄
git reset HEAD

# 單一檔案從索引還原到工作目錄
git reset HEAD file_name

# 還原前一個版本
git reset HEAD^

# 還原前一個版本，檔案丟回工作目錄，預設 mixed，沒有加--mixed 也可以
git reset HEAD^ --mixed

# 還原前一個版本，檔案全部放棄刪除
git reset HEAD^ --hard

# 還原前一個版本，檔案丟回索引
git reset HEAD^ --soft

# 還原到特定 commit
git reset sha-1

# 還原合併前狀態
git reset -hard ORIG_HEAD

# 將特定檔案還原到 working directory
git reset file_name

# 將全部檔案還原到 working directory
git reset .
```

## git reflog

```sh
# 查看詳細歷史紀錄，包含刪除的所有記錄
git reflog
```

## git clean

```sh
# 刪除在工作目錄未加入索引的所有檔案
git clean -f
```

## git config

```sh
# 顯示 git 設定檔
git config --list

# 設定 git 全域使用者名稱
git config --global user.name "user_name"

# 設定 git 全域使用者信箱
git config --global user.email "user_email"

# 設定 git 本地使用者名稱
git config --local user.name "user_name"

# 設定 git 本地使用者信箱
git config --local user.email "user_email"

# 設定使用 vscode 編輯 commit 訊息
git config --global core.editor "code --wait"

# 別名設定(git status 轉換成 git st)
git config --global alias.st status

# my log setting
git config --global alias.lg=log --pretty="%C(yellow)%h %C(green)(%cr)%C(red)%d %C(auto)%s" --graph --all

# my log setting
git config --global alias.lg=log --color --graph --pretty=format:'%Cred%h%Creset-%Cgreen[%cd]%C(yellow)(%cr)%C(bold blue)<%an>%Creset%C(yellow)%d%Creset %s' --date=format:'%Y-%m-%d %H:%M:%S' --abbrev-commit --

# my log setting
git config --global alias.lga=log --all --color --graph --pretty=format:'%Cred%h%Creset-%Cgreen[%cd]%C(yellow)(%cr)%C(bold blue)<%an>%Creset%C(yellow)%d%Creset %s' --date=format:'%Y-%m-%d %H:%M:%S' --abbrev-commit --
```

## git stash

```sh
# 將所有已列入追蹤的檔案建立暫存版本
git stash

# 將所有已列入追蹤的檔案建立暫存版本，save 參數可忽略，結果相同
git stash save

# 將所有已追蹤和未追蹤的檔案建立暫存版本
git stash -u

# 恢復 stash 檔案
git stash pop
```

## git diff

```sh
# 與最近一次 commit 版本比較
git diff

# 與特定 commit 版本比較
git diff commit

# 與特定 commit 版本比較，只顯示檔名
git diff commit --name-only

# 與特定兩個 commit 版本比較
git diff commit1 commit2
```
