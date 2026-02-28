# _blit_process_video(processid,x,y,[width],[height],x0,y0)

## Overview

`_blit_process_video` allows you to blit the video/screen of a different process to a draw target.

## Arguments

### `processid`: integer

The process ID of the process to fetch the video from.

### `x`: integer

The location in the draw target to blit the video from the other process.

### `y`: integer

The location in the draw target to blit the video from the other process.

### `[width]`: integer

Width of the video to capture.

This seems incorrect, and instead requires being the amount of pixels in the canvas, e.g: `480*270` through `width*height` or it wraps weirdly.

### `[height]`: integer

Height of the video to capture

This seems incorrect, instead requiring to be `1` and then later mutated to be correct.

### `x0`: integer

Top left x-coordinate to capture from the process.

### `y0`: integer

Top left y-coordinate to capture from the process.

## Examples

This stores the video of process 3 (wm), which would be the picotron screen, to `/foo.png`.

Snippet from @Soupster (found in the Picotron discord)

```lua
local ud = userdata("u8", 480*270, 1) --create a userdata u8 image

set_draw_target(ud) -- set draw functions to target this userdata
_blit_process_video(3, 0, 0, 480*270, 1, 0, 0) --blit the video from process 3 to the userdata
set_draw_target() -- reset draw target to default

ud:mutate("u8", 480, 270) -- mutate the u8 to be in a bitmap
store("/foo.png", ud) -- store the u8 as an image (png)
```