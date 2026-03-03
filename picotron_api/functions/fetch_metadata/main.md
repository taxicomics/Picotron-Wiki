# fetch_metadata(filename)

## Overview

`fetch_metadata` fetches the (picotron) metadata of a file; this can be from a local path (if it is accessible from the picotron drive) and online.

## Arguments

### `filename`: string

The filename to fetch from.

This can be from online, e.g: from the `bbs://`, `http://` or `https://` protocols.

## Returns

### `meta`: table

The metadata of the requested file