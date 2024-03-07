***
- `%` - go to corresponding bracket
- `i` - inside character, e.g `di"` would delete everything within `"`, works for brackets too
- `a` - ^^ but includes the character as well
> Note: in newer versions of vim, if you are not within the characters when using these motions, it will find the next bit of text which is, e.g using `di{` in this code block: `1234 {5678}` will delete 5678 even if the cursor is on 1234
> Something like `viw` will select the entire word the cursor is on as well
- `W` and `B` - navigates until reaches white space
- `=` - command to auto indent
- `p` - paragraph, e.g `dap` deletes around paragraph, `a` also targets the new line characters and white space while `i` does not
- `o` - while in visual mode will transfer your cursor from top and bottom 
- `<control> + a` - increment number + 1
- `<control> + z` - increment number - 1
- `>`, `<` - indent lines