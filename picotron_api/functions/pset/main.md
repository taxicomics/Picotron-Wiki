# pset(x,y,[col])

## Overview

Sets the pixel at x, y to colour index col (0..63).

## Arguments

### `x`: number
The x position of the pixel

### `y`: number
The y position of the pixel

### `[col]`: number
Default: [current draw color](/picotron_api/functions/color/main.md)

The color of the pixel

## Examples

```lua
for y=0,127 do
    for x=0,127 do
        pset(x, y, x*y/8)
    end
end
```