# set_clipboard(text)

## Overview

`set_clipboard` sets the user's clipboard to `text`.

For structured objects to be copied to the clipboard; use [pod()](/picotron_api/functions/pod/main.md) and [unpod()](/picotron_api/functions/unpod/main.md) with a plaintext format (`0x0` or `0x7`).

This is typically used in conjunction with [get_clipboard()](/picotron_api/functions/get_clipboard/main.md).

## Arguments

### `text`: string

The text to be copied to the clipboard.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
ud = userdata("u8", 64, 64)
set_draw_target(ud)
circfill(32,32,31,8)
circfill(32,32,16,18)
set_draw_target()
set_clipboard(pod(ud, 0x7, {pod_type="image"}))
--> can paste into the code editor
```

```lua
out = "[output]\n"

function _update()

    if key"ctrl" and keyp"c" then
        local test_str = "test"..flr(rnd(10000))
        set_clipboard(test_str)
        out ..= "ctrl-c copied: "..test_str.."\n"
    end

    if key"ctrl" and keyp"v" then
        out ..= "ctrl-v pasted: "..get_clipboard().."\n"
    end

    -- this will only work for clipboard contents that is copied from within Picotron 
    -- (or within the same app when sandboxed), unless pasted with ctrl-v first.
    if key"ctrl" and keyp"b" then
        out ..= "ctrl-b pasted: "..get_clipboard().."\n"
    end
end

function _draw()
    cls()
    print(out, 2,2,7)
end
```