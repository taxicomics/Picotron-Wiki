# all(table)

## Overview

Used in for loops to iterate over all items in a table (that have a 1-based integer index), in the order they were added.

## Arguments

### `table`: table

The table you would like to iterate through.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
t = {11,12,13}
add(t,14)
add(t,"hi")
for v in all(t) do
    print(v)
end -- 11 12 13 14 hi
?#t -- 5
```