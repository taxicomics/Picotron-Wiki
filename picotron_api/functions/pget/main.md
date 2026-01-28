# pget(x,y)

## Overview

Returns the color index at x,y.

## Arguments

### `x`: number
The x position of the pixel

### `y`: number
The y position of the pixel

## Returns
Color index at `x`,`y`.

If the position is out of bounds, the color index will return as `0`.

## Example

```lua
while (true) do
    x, y = rnd(128), rnd(128)
    dx, dy = rnd(4)-2, rnd(4)-2
    pset(x, y, pget(dx+x, dy+y))
end
```