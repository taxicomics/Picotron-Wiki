# rectfill(x0,y0,x1,y1,[col])

## Overview

`rectfill` draws a rectangle with corners at `x0`,`y0` and `x1`,`y1`.

For drawing rectangles that are not filled (just an outline), use [rect](/picotron_api/functions/rect/main.md).

When bit `0x800000000` in col is set, rectfill draws inverted.

## Arguments

### `x0`: number

The top left x-coordinate of the rectangle

### `y0`: number

The top left y-coordinate of the rectangle

### `x1`: number

The bottom right x-coordinate of the rectangle

### `y1`: number

The bottom right y-coordinate of the rectangle

### `[col]`: number

The color of the rectangle; defaults to the last used color.