# music(n, [fade_len], [channel_mask], [base_addr], [tick_offset])

## Overview

Play music starting from pattern `n`.

## Arguments

### `n`: integer

The pattern index to play.

If this is `-1`; it stops music from playing.

### `[fade_len]`: integer

`[fade_len]` is the time (in ms) to fade over a pattern.

### `[channel_mask]`: bitfield

`[channel_mask]` is a bitfield that specifies which channels reserve for music only; low bits first.

### `[base_addr]`: number

When `[base_addr]` is given, the channels used to play music are assigned that location in memory to read data from.

This can be used to load multiple `.sfx` files into memory and play them at the same time.

### `[tick_offset]`: number

An optional offset to start playing from.

This is given in ticks rather than rows as it supports patterns with tricks that play back at different speeds.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

Play only on the first three channels 0..2, the lowest three bits should be set:
```lua
music(0, nil, 0x7) -- bits: 0x1 | 0x2 | 0x4
```

Load some music at `0x80000` and play it without interfering with sound effects stored at the default location of `0x30000`
```lua
fetch("sfx/title.sfx"):poke(0x80000) -- load 256k into 0x80000..0xbffff
music(0, nil, nil, 0x80000) -- play music using 0x80000 as the audio base address
```

Start from row 2 of a track that has spd 16, use
```lua
music(0, nil, nil, nil, 2 * 16)
```