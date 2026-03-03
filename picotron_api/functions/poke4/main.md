# poke4(address,val)

## Overview

`poke4` allows you to poke data `val` (4 bytes) into ram, starting at address `address`.

This cannot be done between processes.

To peek memory, you can use [peek()](/picotron_api/functions/peek/main.md).

The generic poke function is [poke()](/picotron_api/functions/poke/main.md).

## Arguments

### `address`: number

The address to poke into.

### `data`: integer

The data to poke into the address and the following addresses.