# note([pitch], [inst], [vol], [effect], [effect_p], [channel], [retrig], [panning])

## Overview

This provides low level control over the state of a channel.

It is useful in more niche situations, like audio authoring tools and size-coding.

Internally this is what is used to play each row of a sfx when one is active. Use `0xff` to indicate an attribute should not be altered.

## Arguments

### `[pitch]`: number

Channel pitch; default `48` (middle C)

### `[inst]`: number

Instrument index; default `0`

### `[vol]`: number

Volume of the note; default `64`

### `[effectchannel]`: number

Effect; default `0`

### `[effect_p]`: number

Effect parameter; default `0`

### `[channel]`: number

Channel index (`0..15`); default `0`

### `[retrig]`: boolean

Force retrigger; default `false`

### `[panning]`: number

Set channel panning (`-128..127`)

# note()

## Overview

Kill all channels (including leftover echo and decay envelopes).

This is equivalent to
```lua
sfx(-2,-1)
```