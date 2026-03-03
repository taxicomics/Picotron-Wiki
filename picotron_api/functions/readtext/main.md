# readtext([clear])

## Overview

`readtext` is used to consume the next key pressed, this typically works in conjunction with [`peektext()`](/picotron_api/functions/peektext/main.md) and will return only a single character; being the next character in the list to be read.

This is read from the *host* operating system's text entry system.

## Arguments

### `[clear]`: boolean

When `[clear]` is true; *all* remaining text in the queue is discarded.

## Returns

### `textpresent`: boolean

Whether there is text present to be consumed.

## Example

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
while (peektext())
    c = readtext()
    printh("read text: "..c)
end
```