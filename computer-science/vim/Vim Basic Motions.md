***

#### Anatomy of motion:
`command` + `count` + `motion`
e.g to delete 3 lines up:
```
d + 3 + k
``` 

#### Modes
- `i` insert mode (left side of cursor)
- `a` insert mode (right side of cursor)
- `esc` or `<Control> + [` - normal mode  
- `v` visual mode
- `V` visual line mode
- `<control> + v` visual block mode
#### Commands
- `d` - delete
- `c` - delete **and** enter insert mode
- `x` - delete character
- `s` - delete character **and** enter insert mode
- `r` - replace character
- `y` - yank
- `p` - paste
- `v` - select
- `u` - undo
- `<control> + r` - redo

#### Motions
- `h`, `j`, `k` `l` - basic movement
- `w` - move 1 word forward
- `b` - move 1 word backward
