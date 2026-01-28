# fset(n,f,active)

## Overview

Set flag `f` of sprite `n` to boolean `active`.

## Arguments

### `n`: integer
The sprite index.

### `f`: integer
The flag index 0..7

### `active`: boolean
Boolean to set the flag to.

# fset(n,b)

## Overview

Set flags of sprite `n` to bitfield `b`.

## Arguments

### `n`: integer
The sprite index.

### `b`: bitfield
Boolean to set the flags of sprite index to.

## Examples

```lua
fset(2, 1 | 2 | 8)   -- sets bits 0,1 and 3
fset(2, 4, true) -- sets bit 4
print(fget(2))   -- 27 (1 | 2 | 8 | 16)
```