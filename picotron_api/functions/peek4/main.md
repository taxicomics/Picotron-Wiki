# peek4(address)

## Overview

`peek4` peeks into the four memory addresses following `address`.

This cannot be done between processes.

The generic memory peek function is [peek()](/picotron_api/functions/peek/main.md).

## Arguments

### `address`: number

The address to peek from.

## Returns

### `data`: integer

The data in the addresses peeked.