***

- `$` - end of line
- `_` - start of line
- `0` - starting character
- `f + <character>` - move forward **onto** character
- `F + <charactetr>` - move backward **onto** character
- `t + <character>` - move forward **to** character
- `T + <character>` - move backward **to** character
- `;` and `,` - repeats the `f`, `F`, `t`, `T` motion back and forth
- `I` - enter insert mode from start of line
- `A` - enter insert mode from end of line
- `o` - make new line and enter insert mode down
- `O` - make new line and enter insert mode up
- `gM` - middle of line, you can also type a number before it to go the that % of the line
	- e.g `10gM` will go to 10% of the line