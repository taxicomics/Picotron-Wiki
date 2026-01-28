# clip()

## Overview

Resets the clipping mask.

# clip(x, y, w, h, [clip_previous])

## Overview

Sets the clipping rectangle in pixels.

All drawing operations will be clipped to the rectangle at x, y with a width and height of w,h.

Source: [source.lua](source.lua)

## Arguments

### `x`: number
The x position of the clipping rectangle

### `y`: number
The y position of the clipping rectangle

### `w`: number
The width of the clipping rectangle

### `h`: number
The height of the clipping rectangle

### `[clip_previous]`: boolean
When `clip_previous` is true, the new clipping region will be clipped by the old clipping mask.