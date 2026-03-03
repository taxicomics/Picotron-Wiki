# sfx(n, [channel], [offset], [length], [mix_volume])

## Overview

Plays sound effect at index `n` (`0-64`) in channel `[channel]` (`0-15`) for `length` notes.

The volume of the sound effect is `[mix_volume]`.

## Arguments

### `n`: integer

The sound effect index to play.

If this is negative, it calls a special sfx command; these are as follows.

#### -1

Stops playing any sfx on that channel.

The existing channel state is not altered; stopping an sfx that uses an instrument with a long echo will not cut the echo short.

#### -2

Stops playing any sfx on that channel, and also clears the channel state state: echos are cut short  and the channel is immediately silent.

#### -3

Release any looping sfx on that channel

#### -4

Set the mix volume.

The channel mix volume is not reset until sfx() is called on that channel, so music channel mix volumes persist between calls to [`music()`](/picotron_api/functions/music/main.md).

### `[channel]`: integer

The designated channel to play the sound effect in; defaults to a free channel when `-1` or `nil` in one half of the audio channels.

### `[offset]`: number

The offset to play the sfx at; if this is negative, you can delay playback.

### `[length]`: number

The length of the notes to play.

When the sfx is looping, length still means the number of (possibly repeated) notes to play.

### `[mix_volume]`: number

When `[mix_volume]` is given, the channel is mixed at that value (`0x40` means `1.0`).

Otherwise, the value at `0x553a` is used (`0x40` by default).

In addition to the per-channel mix volume, all  channels are subject to a per-process global volume specified at `0x5538` (default: `0x40` == `1.0`).