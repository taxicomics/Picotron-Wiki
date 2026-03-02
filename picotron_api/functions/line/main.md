# line(x0,y0,[x1,y1,[col]])

## Overview

`line` draws a line from `x0`,`y0` to `x1`,`y1`.

## Arguments

### `x0`: number

The first x-coordinate of the line.

### `y0`: number

The first y-coordinate of the line.

### `x1`: number

The second x-coordinate of the line; defaults to the end of the last drawn line.

### `y1`: number

The second y-coordinate of the line; defaults to the end of the last drawn line.

### `[col]`: number

The color of the line; defaults to the last used color.

# line()

## Overview

line() with no parameters means that the next call to line(x1, y1) will only set the end points without drawing.

## Examples

```lua
function _draw()
    cls()
    line()
    for i=0,6 do
        line(64+cos(t()+i/6)*20, 64+sin(t()+i/6)*20, 8+i)
    end
end
```