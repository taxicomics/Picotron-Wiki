# rrect(x,y,width,height,radius,[col])

## Overview

`rrect` draws a rounded rectangle with corners at `x`,`y` with a width of `width` and height of `height`. The radius of the rectangle is `radius`.

For drawing normal rectangles, use [rect](/picotron_api/functions/rect/main.md).

For drawing filled rounded rectangles, use [rrectfill](/picotron_api/functions/rrectfill/main.md).

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