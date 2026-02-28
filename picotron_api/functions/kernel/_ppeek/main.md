# _ppeek(processid,address)

## Overview

`_ppeek`, also known as process peek, allows for a process to peek into the memory of another process, returning the data stored at the memory address `address` in the process under the PID `processid`.

## Arguments

### `processid`: integer

The process ID of the process to fetch from.

### `address`: integer

The memory address (max: 65536) of the process to fetch from.

## Returns

### `byte`: integer

The byte at address `address` in process with the process id `processid`.