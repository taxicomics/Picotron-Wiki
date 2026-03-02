# split(string,[seperator],[convert_numbers]): table

## Overview

`split` converts the string `string` into a table, being seperated by the seperator `[seperator]`.

Elements in the table are automatically converted into numbers if they are a number as a string (e.g: "2"); this can be disabled by settings `[convert_numbers]` to false.

This can also be used in the form of `string:split([seperator],[convert_numbers])`.

## Arguments

### `string`: string

The string to split into a table.

### `[seperator]`: string|number

When seperator is a string, it splits the string each time it hits the seperator string.

When seperator is a number, the string is split into n-character groups.

### `[convert_numbers]`: boolean

A truthy boolean of whether to convert number strings into numbers; defaults to true.

## Returns

### `table`: table

Returns the string split into a table.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
?split("1,2,3,a,b")   -- {1,2,3,"a","b"}
?split("one:two:3",":",false) -- {"one","two","3"}
?split("1,,2,")   -- {1,"",2,""}
```