# pod(val,[flags],[metadata]): string

## Overview

`pod` returns a binary string encoding the value `val`.

Functions and other non-encodable values can be present in this input; but are replaced with nil and cannot be unpodded.

## Arguments

### `val`: any

The value to pod/encode.

When `val` is a table which contains circular references, `pod()` returns nil.

### `[flags]`: number

> If `[flags]` is a table, it acts as `[metadata]`

`[flags]` is a number, typically represented in hex, which controls how the output string is encoded; `0x00` is the default.

#### Available Flags:

* 0x00 plaintext (& valid Lua)
* 0x01 pxu encode userdata in a compressed (RLE-style) form
* 0x02 lz4 binary compression pass (dictionary matching)
* 0x04 base64 text encoding (convert back into a text-friendly format)
* 0x08 (reserved for future use -- should be 0)
* 0x10 pxu option: store raw (smaller for already-compressed userdata)
* 0x20 strings option: store raw binary, instead of escaped plain-text
* 0x40 (reserved for future use -- should be 0)
* 0x80 pxu option: store in a stable rle format (used for undo stacks)


Plaintext (`0x00`) PODs can get quite large if they contain images or map data.

A compressed binary encoding can be generated using flags `0x1` and `0x2`, which are normally used together as the pxu format aims to produce output that can be further compressed by lz4.

[store()](/picotron_api/functions/store/main.md) and [send_message()](/picotron_api/functions/send_message/main.md) uses this format by default.


The flag `0x4` is used to encode a compressed string back into a plaintext format that can be used with the clipboard and is also used for things like embedded images in text (try copying and pasting from the sprite editor into the code editor).

```lua
?pod({a=1,b=2}, 0x7)
unpod("b64:bHo0AAoAAAAJAAAAkHthPTEsYj0yfQ==")
```

Note that the output of `0x7` is still a legal lua snippet that returns the original value `{a=1,b=1}`.
In this case the resulting string is larger than raw encoding even though it is compressed, because of the overhead of bookkeeping information stored at each layer of encoding.

### `[metadata]`: table

When the second (`[flags]`) or third parameter is a table, it is taken to be `[metadata]`.

This acts as metadata also encoded into the pod.

## Returns

### `podded`: string

The encoded string from value `val`.

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
?pod({a=1,b=2}) --{a=1,b=2}
```

```lua
podded=pod("some text", {author="alice"}) -- --[[pod,author="alice"]]"some text"
?podded

value,meta=unpod(podded)

?value --"some text"
?pod(meta) -- "{author='alice'}"
```

```lua
?pod({a=1,b=2}, 0x7)
unpod("b64:bHo0AAoAAAAJAAAAkHthPTEsYj0yfQ==")
```