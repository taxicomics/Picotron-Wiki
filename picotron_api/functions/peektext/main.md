# peektext()

## Overview

`peektext` is used to see whether text has been entered; this will always return the same key until [`readtext()`](/picotron_api/functions/readtext/main.md) consumes it.

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