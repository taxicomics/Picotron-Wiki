# cursor(x,y,[col])

## Overview

`cursor` sets the cursor position to `x`,`y`.

If `[col]` is set, it also sets the color of the cursor.

This is modifying the text cursor, *not* the mouse pointer; for that, see [mouse()](/picotron_api/functions/mouse/main.md)

## Arguments

### `x`: number

The new x-coordinate of the cursor.

### `y`: number

The new y-coordinate of the cursor.

### `[col]`: number

The new color of the cursor.