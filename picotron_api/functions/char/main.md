# char(...): string

## Overview

`char` returns a string formed from the character codes in `...`.

## Arguments

### `...`

`...` is one or more arguments, each argument being a character code (0-255).

## Returns

### `string`: string

The string formed from the character codes.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
?chr(64)-- "@"
?chr(104,101,108,108,111)   -- "hello"
```
