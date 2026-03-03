# mouselock(lock, event_sensitivity, move_sensitivity)

## Overview

`mouselock` is used to make a request to the host operating system's window manager to capture the mouse, allowing for it to control sensitivity and movement speed.

This returns the relative position since the last frame

## Arguments

### `lock`: boolean

Whether to lock the mouse or not

### `event_sensitivity`: number

A number between 0 and 4 that determines how fast dx,dy changes (1.0 == 1/picotron pixel)

### `move_sensitivity`: number

A number between 0 and 4 that determines the mouse sensitivity (1.0 == normal speed)

## Returns

### `dx`: number

The distance on the x-axis that the mouse pointer has moved

### `dy`: number

The distance on the y-axis that the mouse pointer has moved

## Example

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
local size, col = 20, 16
function _draw()
    cls()
    circfill(240, 135, size*4, col)
    local _,_,mb = mouse()
    dx,dy = mouselock(mb > 0, 0.05, 0) -- dx,dy change slowly, stop mouse moving
    size += dx  --  left,right to control size
    col  += dy  --  up,down to control colour
end
```