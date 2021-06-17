# Vim

- [Vim](#vim)
  - [Insert Mode](#insert-mode)
  - [Normal Mode](#normal-mode)
  - [Window Control](#window-control)
  - [Move Cursor](#move-cursor)
  - [Search](#search)
  - [Visual Mode](#visual-mode)
  - [Copy, Paste](#copy-paste)
  - [Edit Multiple File](#edit-multiple-file)
  - [Buffer/Window/Tab](#bufferwindowtab)
  - [Text Object](#text-object)

> `vimtutor` open tutorial

> `:help` open manual

## Insert Mode

- `i` into insert mode
- `I` into start of line
- `o` new line
- `O` upon cursor line
- `a` append before cursor
- `A` into end of line
- `x` delete
- `d` delete (need select)
- `D` delete from cursor to end of line
- `dd` delete whole line
- `c` delete (need select) and into insert mode
- `C` delete from cursor to end of line and into insert mode
- `r` replace cursor character
- `>>` increase indent (`:set shiftwidth` set indent width)
- `<<` decrease indent
- `3>>` three line indent (or select three line `>`)
- `=` selected code auto indent
- `~` case convert
- `.` repeat last operate
- `J` merge line
- `ctrl` + `w` delete one word
- `ctrl` + `u` delete content from cursor to start

## Normal Mode

- `esc`
- `ctrl` + `[`
- `:!` + `command` command in terminal
- `:r` + `command` copy cand paste command result

## Window Control

- `ctrl` + `z` put vim in background
- `fg` return to vimi
- `zz` put line middle of window
- `zt` put line top of window
- `zb` put line bottom of window

## Move Cursor

- `h` left
- `j` down
- `k` up
- `l` right
- `w` next word
- `W` next word (skip mark)
- `b` back word
- `B` back word (skip mark)
- `}` next paragraph
- `{` back paragraph
- `gg` document top
- `G` document bottom
- `0` start of line(contain indent)
- `ctrl` + `^` start of line
- `$` line end
- `gk` back line
- `gj` next line
- `10G` move to number 10 of line
- `ctrl` + `f` page down
- `ctrl` + `b` page up
- `zf` fold content (need select)
- `zd` unfold content (or `l`)
- `zfip` fold content

## Search

- `/` search (`:set hlsearch` set search result hightlight)
- `n` next search result
- `N` prev search result
- `?` search (reverse)
- `n` prev search result
- `N` next search result
- `*` search cursor word
- `#` search cursor word (reverse)
- `f` + `a` search next `a` in same line
- `F` + `a` search next `a` in same line (reverse)

## Visual Mode

- `v` into visual mode
- `V` visual line
- `ctrl` + `v` visual block mode (`I` into insert mode)
- `vw` select word (contain last space)
- `viw` select inner word
- `vaw` select a word (around)
- `vit` select inner tag (html -> textContent)
- `vat` select a tag (html -> contain tag)
- `vi"` select word in double quotes
- `vi"` select word in double quotes (contain double quotes)
- `v}` select block
- `v{` select block (reverse)
  > `v` can replace to `d`(delete) or `c`(change)

## Copy, Paste

- `y` copy (yank)
- `p` paste after cursor
- `P` paste before cursor
- `3` + `p` paste three times
- `yy` copy whole line
- `3yy` copy three line
- `u` undo
- `ctrl` + `r` redo
- `"` + `a` + `y` copy word to register (a ~ z)
- `"` + `a` + `p` paste `a` register word
- `:reg` view all register content (vim has 48 register)
- `:set clipboard=unnamed` let vim can use computer clipboard

## Edit Multiple File

- `:e <Filename>` open file
- `:tabe` open tab
- `:tabe <Filename>` open file in tab
- `gt` switch between tab
- `gT` switch between tab (reverse)
- `:new` split window (horizontal)
- `:vnew` split window (vertical)
- `ctrl` + `w` +`w` switch between split window
- `ctrl` + `w` + `j` or `k` switch between split window
- `vi` + `-o` + `<Filename>` open multiple file (horizontal)
- `vi` + `-O` + `<Filename>` open multiple file (vertical)
- `vi` + `-o` or `O` + `*` open all file
- `vi` + `-p` + `<Filename>` or `*` open file (tab)

## Buffer/Window/Tab

1. Buffer -> store data

   A buffer is the in-memory text of a file.

2. Window -> show data

   A window is a viewport in a buffer.

3. Tab -> arrange data

   A tab page is a collection of windows.

- `:ls` show is open file list
- `:b3` open buffer number 3 file
- `:bnext` or `:bn` next buffer
- `bprevious` or `bp` previous buffer
- `blast` or `bl` last buffer
- `bfirst` or `bf` first buffer
- `%a` current buffer
- `#` prev buffer
- `ctrl` + `^` back to prev buffer
- `:b` + `<Filename>` to specific file
- `bdelete` or `bd` close buffer
- `:tab ba` all buffer to tab (`:tab ball`)

For example:

```
$ :ls

  1. %a "index1.html"
  2.    "index2.html"
  3. #  "index3.html"

$ :b3 open buffer number 3 file

```

## Text Object

- Noun

  - `w` = word
  - `s` = sentence
  - `p` = paragraph
  - `t` = tag
  - `'`, `"`, `(`, `)`, `[`, `]`, `{`, `}`

- Verb

  - `y` = yank
  - `p` = paste
  - `d` = delete
  - `c` = change

- Range

  - `i` = inner
  - `a` = a or around

- Measure

  - number

- Example
  - `vis` select inner sentence
  - `vip` select inner paragraph
  - `v3w` select three word
