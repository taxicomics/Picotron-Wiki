# exit(unknown)

## Overview

`exit` immediately closes the program; this can be used to terminate a terminal program early.

## Arguments

### `unknown`: unknown

Argument observed; seemingly useless.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
s = input("would you like to continue? [y/n] ")
if (s == "n") exit(0)
```