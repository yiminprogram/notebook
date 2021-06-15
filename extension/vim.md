# Vim Command

## Insert Mode

- `i` into insert mode
- `o` new line
- `a` append before cursor

## Normal Mode

- `esc`
- `ctrl` + `[`

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
- `0` line start
- `$` line end
- `gk` back line
- `gj` next line

## Search

hightlight search results

> :set hlsearch

- `/` search
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
- `V` select whole line

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
