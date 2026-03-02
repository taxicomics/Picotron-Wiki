# foreach(table,callback)

## Overview

Iterate over the table `table` and call the callback function `callback` for each element.

## Arguments

### `table`: table

The table you would like to iterate through.

### `callback`: function

The function to callback for each element; this gets called in the form of

```lua
callback(element_value)
```

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
foreach({1,2,3}, print)
```