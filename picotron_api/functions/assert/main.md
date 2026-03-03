# assert(condition,[message])

## Overview

`assert` stops the program and prints the message given if `condition` is false.

This is useful for debugging cartridges by asserting things that you expect to be true are indeed true.

## Arguments

### `condition`: boolean

A condition to be asserted; e.g: (`player.x>10`)

### `[message]`: string

A message that is printed when the process is asserted

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
assert(actor)  --  actor should exist and be a table
actor.x += 1   --  definitely won't get a "referencing nil" error
```