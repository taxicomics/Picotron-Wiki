# ovalfill(x0,y0,x1,y1,[col])

## Overview

`oval` draws an oval that is symmetrical in x and y (an ellipse), with the given bounding rectangle.

For drawing circles, use [circfill](/picotron_api/functions/circfill/main.md).

When bit `0x800000000` in col is set, ovalfill is drawn inverted.

## Arguments

### `x0`: number

The top left x-coordinate of the oval

### `y0`: number

The top left y-coordinate of the oval

### `x1`: number

The bottom right x-coordinate of the oval

### `y1`: number

The bottom right y-coordinate of the oval

### `[col]`: number

The color of the oval; defaults to the last used color.