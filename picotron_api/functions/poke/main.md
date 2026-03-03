# poke(address,data,[...])

## Overview

`poke` allows you to poke data into ram, starting at address `address`.

This cannot be done between processes.

To peek memory, you can use [peek()](/picotron_api/functions/peek/main.md).

## Arguments

### `address`: number

The address to poke into.

### `data`: integer

The data to poke into the address.

### `[...]`: integer

This can be continued to poke up to 65536 pieces of data into the consecutive 65536 addresses past `address`.

They are identical to the `data` argument; being offset by +1.