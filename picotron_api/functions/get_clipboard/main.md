# get_clipboard()

## Overview

`get_clipboard` fetches the user's clipboard.

For security reasons, get_clipboard() only has access to the host clipboard after ctrl-v is pressed while Picotron is active.

Until ctrl-v is pressed, changes to the host clipboard have no effect on the return value of get_clipboard().

The same is true for sandboxed applications (e.g. bbs carts); they are only able to access clipboard contents from other processes once ctrl-v is pressed while that app has keyboard focus.

This is typically used in conjunction with [set_clipboard()](/picotron_api/functions/set_clipboard/main.md).

## Returns

### `clipboard`: string

The clipboard that is fetched from the user.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

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