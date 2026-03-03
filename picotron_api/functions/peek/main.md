# peek(address,[bytes])

## Overview

`peek` allows you to peek into ram at address `address`.

This can not be done between processes; you can technically do this with kernel functions through the use of [`_ppeek`](/picotron_api/functions/kernel/_ppeek/main.md).

To poke memory, you can use [poke()](/picotron_api/functions/poke/main.md).

## Arguments

### `address`: number

The address to peek.

### `[bytes]`: integer

The amount of bytes to read; default 1, maximum 65536.

## Returns

### `byte`: integer

The byte at address `address`.

### `[...]`: integer

The consecutive bytes, the amount of bytes read is the `[bytes]` argument.
## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

Read the first 2 bytes of video memory.
```lua
a, b = peek(0x10000, 2)
```