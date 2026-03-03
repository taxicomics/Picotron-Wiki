# rrectfill(x,y,width,height,radius,[col])

## Overview

`rrect` draws a filled rounded rectangle with corners at `x`,`y` with a width of `width` and height of `height`. The radius of the rectangle is `radius`.

When bit `0x800000000` in col is set, rrectfill draws inverted.

For drawing normal filled rectangles, use [rectfill](/picotron_api/functions/rectfill/main.md).

For drawing rounded rectangles (no filling, just outline), use [rrect](/picotron_api/functions/rrect/main.md).

## Arguments

### `x`: number

The x-coordinate of the rounded rectangle

### `y`: number

The y-coordinate of the rounded rectangle

### `width`: number

The width of the rounded rectangle; must be more than 0

### `height`: number

The height of the rounded rectangle; must be more than 0

### `radius`: number

The radius of the rounded rectangle; defaults to 0.

The radius is clamped to `min(width,height)/2`

### `[col]`: number

The color of the rectangle; defaults to the last used color.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

Draw a red (colour 8) rounded rectangle 40 pixels wide and 30 pixels talls with 3 pixels missing at each corner (radius 2):
```lua
rrectfill(100,50,40,30,2,8)
```