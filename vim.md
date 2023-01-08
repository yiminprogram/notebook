# Vim

## Move

- `h` left
- `j` down
- `k` up
- `l` right
- `w` next word
- `W` next word (skip mark)
- `b` previous word
- `B` previous word (skip mark)
- `}` next paragraph
- `{` previous paragraph
- `gg` document top
- `G` document bottom
- `0` start of line
- `ctrl` + `^` start of line
- `$` end of line
- `gk` previous line
- `gj` next line
- `10G` move to line number of 10
- `ctrl` + `f` page down
- `ctrl` + `b` page up

## Insert

- `i` insert
- `I` insert (start of line)
- `o` new line (after current line)
- `O` new line (before current line)
- `a` insert (after cursor)
- `A` insert (end of line)

## Delete

- `x` delete char
- `d` delete selection
- `D` delete to end of line
- `dd` delete whole line
- `ctrl` + `w` delete one word before cursor
- `ctrl` + `u` delete from cursor to start

## Insert And Delete

- `c` delete selection and enter insert
- `C` delete to end of line, and enter insert

## Replce

- `r` replace char

## Indent

- `>>` increase indent
- `<<` decrease indent
- `3>>` 3 line indent
- `>` selected line increase indent
- `<` selected line decrease indent
- `=` selection auto indent

## Other

- `~` case convert
- `.` repeat last operation
- `J` merge line

## Window Control

- `zz` center
- `zt` top
- `zb` bottom

## Search

- `/` search
- `?` search (reverse)
- `n` next search result
- `N` previous search result
- `*` search cursor word
- `#` search cursor word (reverse)
- `f` + `a` search next `a` at current line
- `F` + `a` search next `a` at current line (reverse)

## Select (Visual Mode)

- `v` select char
- `V` select line
- `ctrl` + `v` select multiple (`I` insert mode)
- `vw` select from current word to next word first char
- `viw` select inner word
- `vaw` select from current word to last space
- `vit` select tag content
- `vat` select tag content and tag
- `vi"` select word in `""`
- `va"` select word in `""` and `""`
- `v}` select block
- `v{` select block (reverse)

> `v` can replace to `d` (delete) or `c` (change)
