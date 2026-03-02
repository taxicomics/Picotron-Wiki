# create_delta(str0,str1): string

## Overview

`create_delta` returns a string encoding (acting as a delta) which provides all the information needed to get from `str0` to `str1`.

This can be used with [`apply_delta()`](/picotron_api/functions/apply_delta/main.md) to create `str1` from `str0` and the delta.

Deltas are useful for undo stacks and changes in gamestates being sent across a network; the binary format of the delta includes a few safety features such as crc and length checks to ensure the input and output strings are as expected. The first 4 bytes of the delta string are always `dst\0`.

## Arguments

### `str0`: string

The original string, the delta being a transformation from this string to this `str1`.

### `str1`: string

The new string, the delta being a transformation from `str0` to this string.

## Returns

### `delta`: string

A string encoding that provides all the information to get from `str0` to `str1`.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

Simple change between two strings
```lua
str0="The quick brown fox"
str1="The quick red fox"

delta=create_delta(str0,str1) -- delta that changes the "brown" into "red"

?apply_delta(str0) -- str1
```

Used with [pod()](/picotron_api/functions/pod/main.md) and [unpod()](/picotron_api/functions/unpod/main.md) to encode the changes between tables.

```lua
a = {1,2,3}
b = {1, "banana", 2, 3}
delta = create_delta(pod(a), pod(b)) -- pod is a string, so it can be used to create deltas

b2=apply_delta(pod(a),delta) -- identical to b (as a string)

b=unpod(b2) -- identical to original b
```