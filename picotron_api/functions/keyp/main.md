# keyp(k,[raw])

## Overview

`keyp` queries wheter a keyboard key is pressed.

By default, `keyp()` uses the local keyboard layout; On an AZERTY keyboard, `keyp("a")` is true when the key to the right of `Tab` is pressed.

You can use the raw layout by setting `[raw]` to true and using `k` as a raw scancode.

To get the raw layout, use true as the second parameter to indicate that `k` should be the name of the raw scancode.

This is typically used in menus or grid-based player movement.

The state that keyp() reads is reset at the start of each call to [_update()](/picotron_api/program_structure/main.md), so it is preferable to use keyp only from inside that call and not from [_draw()](/picotron_api/program_structure/main.md), which might be called less frequently.

For keyboard state, use [key](/picotron_api/functions/key/main.md).

For controller button presses, use [btnp](/picotron_api/functions/btn/main.md).

## Arguments

### `k`: string

The name of each key is the same as the character it produces on a US keyboard with some exceptions: "space", "delete", "enter", "tab", "ctrl", "shift", "alt", "pageup", "pagedown".

#### When `[raw]` is not true

The key to query whether it's pressed or not.

#### When `[raw]` is true

The raw scancode whether it's pressed or not.

### `[raw]`: boolean

Whether or not `k` is a raw scancode.

## Returns

### `pressed`: boolean

Returns `true` when the requested key is pressed, `false` otherwise.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

Whether the key to the right of `CAPSLOCK` is pressed, regardless of local keyboard layout.
```lua
?keyp("a", true)
```

Keybind example
```lua
if (key"ctrl" and keyp"a") printh("CTRL-A Pressed")
```

# keyp()

## Overview

Returns true when any key is pressed.

## Returns

### `down`: boolean

Returns `true` when any key is pressed, `false` otherwise.