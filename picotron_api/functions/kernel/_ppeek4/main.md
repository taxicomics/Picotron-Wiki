# _ppeek4(processid,address)

## Overview

`_ppeek4` allows for a process to peek into the memory of another process, returning the 4 consecutive bytes stored at the memory address `address` and the proceeding 3 bytes in the process under the PID `processid`.

## Arguments

### `processid`: integer

The process ID of the process to fetch from.

### `address`: integer

The memory address (max: 65536) of the process to fetch from.

## Returns

### `bytes`: integer

The 4 bytes that were fetched.