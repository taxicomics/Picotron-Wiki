# _userland_to_kernal_path(path, [mode])

## Overview

`_userland_to_kernal_path` converts a userland path, e.g: `/foo.txt` to a kernal path and returns the kernal path.

## Arguments

### `path`: string

The kernel path of the file.

### `[mode]`: string

The mode for the path

#### One of four:

* `R` Read-only
* `RW` Read-Write
* `W` Write-only
* `X` Unknown