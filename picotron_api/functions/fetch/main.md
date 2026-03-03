# fetch(filename,[options])

## Overview

`fetch` fetches a file; this can be from a local path (if it is accessible from the picotron drive) and online.

Unless this is an online fetch with `on_complete` in the options, it is a blocking function and stalls the process.

This returns the filedata and the metadata.

## Arguments

### `filename`: string

The filename to fetch from.

This can be from online, e.g: from the `bbs://`, `http://` or `https://` protocols.

### `[options]`: table

This is used for `http`/`https` requests.

The available options are:

#### `on_complete`: function

A callback method that is called with the filedata when it fetches; this makes fetch non-blocking and asynchronous.

## Returns

This does not return anything when `[options].on_complete` is present as it becomes asynchronous.

### `filedata`: any

The filedata of the file.

### `meta`: table

The metadata of the file; seems to fail with local fetches.