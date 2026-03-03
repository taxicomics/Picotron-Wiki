# key(k,[raw])

## Overview

`key` queries the key state of a keyboard key.

By default, `key()` uses the local keyboard layout; On an AZERTY keyboard, `key("a")` is true when the key to the right of `Tab` is pressed.

You can use the raw layout by setting `[raw]` to true and using `k` as a raw scancode.

To get the raw layout, use true as the second parameter to indicate that `k` should be the name of the raw scancode.

For keyboard key presses, use [keyp](/picotron_api/functions/keyp/main.md).

For controller inputs, use [btn](/picotron_api/functions/btn/main.md).

## Arguments

### `k`: string

The name of each key is the same as the character it produces on a US keyboard with some exceptions: "space", "delete", "enter", "tab", "ctrl", "shift", "alt", "pageup", "pagedown".

#### When `[raw]` is not true

The key to query the state of.

#### When `[raw]` is true

The raw scancode to query the state of

### `[raw]`: boolean

Whether or not `k` is a raw scancode.

## Returns

### `down`: boolean

Returns `true` when the requested key is down, `false` otherwise.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

Whether the key to the right of `CAPSLOCK` is held, regardless of local keyboard layout.
```lua
?key("a", true)
```

Keybind example
```lua
if (key"ctrl" and keyp"a") printh("CTRL-A Pressed")
```

```lua
function _draw()
    cls(1)
    -- draw when either shift key is held down
    if (key("shift")) circfill(100,100,40,12)
end
```

# key()

## Overview

Returns true when any key is down.

## Returns

### `down`: boolean

Returns `true` when any key is down, `false` otherwise.