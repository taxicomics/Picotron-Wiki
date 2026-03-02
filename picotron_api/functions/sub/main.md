# sub(str,pos0,pos1): string

## Overview
`sub` returns a substring of the string `sub`, similar to Lua's default [`string.sub`](https://www.lua.org/pil/20.html) (which is also available in Picotron).

This can also be used in the form of `string:sub()`, where `string` becomes the first argument, `str`.

## Arguments

### `str`: string
The string to acquire the substring of.

### `pos0`: integer
The first position of the substring (character index).

Positions are 1-indexed, similar to tables, so the first character is at index 1.

### `pos1`: integer|nil
The second position of the substring (character index), if this is `nil`, it defaults to the value in `pos0`.

Positions are 1-indexed, similar to tables, so the first character is at index 1.

## Returns

### `substring`: string
The substring of the string.

## Example
```lua
local string="Hello world"

?sub(string,1,5) -- "Hello"
?sub(string,7) -- "World"
?string:sub(1,5) -- "H"
```