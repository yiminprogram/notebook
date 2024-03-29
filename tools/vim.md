# Vim

## 移動

- `h` 游標左移
- `j` 游標下移
- `k` 游標上移
- `l` 游標右移
- `w` 右移一個單字
- `W` 右移一個單字(忽略標點符號)
- `b` 左移一個單字
- `B` 右移一個單字(忽略標點符號)
- `}` 下一個段落
- `{` 上一個段落
- `gg` 移到文件最上面
- `G` 移到文件最下面
- `0` 移到行首
- `ctrl` + `^` 移到行首
- `$` 移到行尾
- `gk` 移到上一行
- `gj` 移到下一行
- `10G` 移到第十行
- `ctrl` + `f` 下一頁
- `ctrl` + `b` 上一頁

## Insert 模式

- `i` 進入 insert 模式
- `I` 行首新增
- `o` 下方新增一行
- `O` 上方新增一行
- `a` 游標後新增
- `A` 行尾新增

## 刪除 (Delete)

- `x` 刪除一個字元
- `d` 刪除選擇部份
- `D` 刪除游標到行尾
- `dd` 刪除一整行
- `ctrl` + `w` 刪除游標前一個單字
- `ctrl` + `u` 刪除游標到行首

## 更改 (Change)

- `c` 刪除選取部份，進入 insert 模式
- `C` 刪除游標到行尾，進入 insert 模式

## 替換 (Replace)

- `r` 更改字元

## 縮排 (Indent)

- `>>` 增加縮排
- `<<` 減少縮排
- `3>>` 增加３個縮排
- `>` 選取部份增加縮排
- `<` 選取部份減少縮排
- `=` 選取部份自動縮排

## 視窗移動

- `zz` 游標移至中間
- `zt` 游標移至上方
- `zb` 游標移至下方

## 搜尋

> `:set hlsearch`設定結果高亮，enter 後進入結果，`:noh`關閉高亮)

- `/` 搜尋
- `?` 反向搜尋
- `n` 移至下一個結果
- `N` 移至上一個結果
- `*` 搜尋游標所在的單字
- `#` 反向搜尋游標所在的單字
- `f` + `a` 搜尋同一行下一個`a`的字元
- `F` + `a` 反向搜尋同一行下一個`a`的字元

## 選取 (Visual Mode)

- `v` 選取字元
- `V` 選取行
- `ctrl` + `v` 新增游標選取，`I`進入 Insert 模式
- `vw` 選取單字包含最後空白至下一個單字第一個字元
- `viw` 選取單字
- `vaw` 選取單字及空白
- `vit` 選取標籤內容
- `vat` 選取標籤內容及標籤
- `vi"` 選取`""`中內容
- `va"` 選取`""`中內容及`""`
- `v}` 選取區塊
- `v{` 反向選取區塊

> `v` 可以更換成 `d` (刪除) 或 `c` (修改)

## 其他操作

- `~` 更改大小寫
- `.` 重複最後操作
- `J` 選取部份合併
