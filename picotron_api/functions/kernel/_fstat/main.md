# _fstat(kernel_path)

## Overview

`_fstat` returns the file status of the kernel path, `kernel_path`.

## Arguments

### `kernel_path`: string

The kernel path to fetch the file status of.

This can not have a protocol, e.g: `bbs://`.

## Returns

### `filestatus`: string

The file status of the kernel path.