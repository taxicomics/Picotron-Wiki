# fillp(p)

## Overview

Set a 4x4 fill pattern using PICO-8 style fill patterns.

`p` is a bitfield in reading order starting from the highest bit.

This affects [circ](/picotron_api/functions/circ/main.md), [circfill](/picotron_api/functions/circfill/main.md), [oval](/picotron_api/functions/oval/main.md), [ovalfill](/picotron_api/functions/ovalfill/main.md), [rect](/picotron_api/functions/rect/main.md), [rectfill](/picotron_api/functions/rectfill/main.md), [pset](/picotron_api/functions/pset/main.md), [line](/picotron_api/functions/line/main.md).

Fill patterns in Picotron are 64-bit specified 8 bytes from 0x5500, where each byte is a row (top to bottom) and the low bit is on the left.

## Arguments

### `p`: bitfield

A bitfield in reading order starting from the highest bit

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

Draw a red (colour 8) rounded rectangle 40 pixels wide and 30 pixels talls with 3 pixels missing at each corner (radius 2):
```lua
rrectfill(100,50,40,30,2,8)
```

# fillp(1,2,3,4,5,6,7,8)

## Overview

Sets a 8x8 fill pattern.
This affects [circ](/picotron_api/functions/circ/main.md), [circfill](/picotron_api/functions/circfill/main.md), [oval](/picotron_api/functions/oval/main.md), [ovalfill](/picotron_api/functions/ovalfill/main.md), [rect](/picotron_api/functions/rect/main.md), [rectfill](/picotron_api/functions/rectfill/main.md), [pset](/picotron_api/functions/pset/main.md), [line](/picotron_api/functions/line/main.md).

To define an 8x8 with high bits on the right (so that binary numbers visually match), fillp can be called with 8 arguments.

### Arguments

#### `1`: bitfield

Bitfield with high bits on the right

#### `2`: bitfield

Bitfield with high bits on the right

#### `3`: bitfield

Bitfield with high bits on the right

#### `4`: bitfield

Bitfield with high bits on the right

#### `5`: bitfield

Bitfield with high bits on the right

#### `6`: bitfield

Bitfield with high bits on the right

#### `7`: bitfield

Bitfield with high bits on the right

#### `8`: bitfield

Bitfield with high bits on the right

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
fillp(
    0b10000000,
    0b01011110,
    0b00101110,
    0b00010110,
    0b00001010,
    0b00000100,
    0b00000010,
    0b00000001
)
```