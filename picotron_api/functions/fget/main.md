# fget(n,f)

## Overview

Retrieve the flag(s) of sprite `n`.

The initial state of flags 0..7 are settable in the sprite editor, so can be used to create custom sprite attributes.
## Arguments

### `n`: integer
The sprite index.

### `f`: integer
The flag index 0..7

## Returns
Flag `f` as a boolean of sprite `n`

# fset(n)

## Overview

Retrieve the flag bitfield of sprite `n`.

## Arguments

### `n`: integer
The sprite index.

## Returns
The bitfield of flags of sprite `n`.

## Examples

```lua
fset(2, 1 | 2 | 8)   -- sets bits 0,1 and 3
fset(2, 4, true) -- sets bit 4
print(fget(2))   -- 27 (1 | 2 | 8 | 16)
```