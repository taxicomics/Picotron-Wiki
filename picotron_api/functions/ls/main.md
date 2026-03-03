# ls([directory])

## Overview

`ls` returns the files and folders in the given path relative to the current working directory.

## Arguments

### `[directory]`: string|nil

The relative path to list the files and folders of.

If this is blank; this lists the files and folders of the current working directory.

If this starts with `/`; it is an exact path and the current working directory plays no effect.

## Returns

### `list`: table

A table of the files and folders in the directory; this is relative to the directory and will not be the fullpath.