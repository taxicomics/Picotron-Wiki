# circfill(x,y,r,[col])

## Overview

`circ` draws a filled circle at `x`,`y` with radius `r`.

If `r` is negative, the circle is not drawn.

For drawing a circle that isn't filled (just an outline), see [`circ()`](/picotron_api/functions/circ/main.md).

When bit `0x800000000` in col is set, circfill draws inverted (everything outside the circle is drawn).

## Arguments

### `x`: number

The x-coordinate of the circle

### `y`: number

The y-coordinate of the circle

### `r`: number

The radius of the circle

### `[col]`: number

The color of the circle; defaults to the last used color.