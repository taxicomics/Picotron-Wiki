# del(table,value)

## Overview

`del` deletes the value `value` from the table `table`.
Without an index, it is equivalent to:

```lua
tbl[#tbl + 1] = val
```

## Arguments

### `table`: table

The table you would like to add `value` to.

### `value`: any

The value to add into the table `table`

### [index]: integer

The index of where to place the item in the table `table`, defaults to the end of the table.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
foo={}-- create empty table
add(foo, 11)
add(foo, 22)
?foo[2] -- 22
```