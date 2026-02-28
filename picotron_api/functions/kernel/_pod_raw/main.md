# _pod_raw(obj, [flags], [meta_str])

## Overview

`_pod_raw` acts nearly identically to [`pod()`](/picotron_api/functions/pod/main.md), encoding lua values; excluding functions.

`_pod` is an alias for this function.

## Arguments

### `obj`: any

Any data type,

### `flags`: integer

The flags to be used when podding.

#### Available Flags:

* 0x01 pxu encode userdata in a compressed (RLE-style) form
* 0x02 lz4 binary compression pass (dictionary matching)
* 0x04 base64 text encoding (convert back into a text-friendly format)
* 0x08 (reserved for future use -- should be 0)
* 0x10 pxu option: store raw (smaller for already-compressed userdata)
* 0x20 strings option: store raw binary, instead of escaped plain-text
* 0x40 (reserved for future use -- should be 0)
* 0x80 pxu option: store in a stable rle format (used for undo stacks)

### `[meta_str]`: string

Metadata stored as a string. This is generated in `/system/lib/fs.lua` with:

```lua
local function _generate_meta_str(meta_p)

	-- use a copy so that can remove pod_format without sideffect
	-- _pod is wrapped version -- protects again circularities
	local meta = _unpod(_pod(meta_p)) or {}

	local meta_str = "--[["

	if (meta.pod_format and type(meta.pod_format) == "string") then
		meta_str ..= "pod_format=\""..meta.pod_format.."\""
		meta.pod_format = nil -- don't write twice
	elseif (meta.pod_type and type(meta.pod_type) == "string") then
		meta_str ..= "pod_type=\""..meta.pod_type.."\""
		meta.pod_type = nil -- don't write twice
	else
		meta_str ..= "pod"
	end

	local meta_str1 = _pod(meta, 0x0) -- 0x0: metadata always plain text. want to read it!

	if (meta_str1 and #meta_str1 > 2) then
		meta_str1 = sub(meta_str1, 2, #meta_str1-1) -- remove {}
		meta_str ..= ","
		meta_str ..= meta_str1
	end

	meta_str..="]]"

	return meta_str
end
```

## Returns

The podded form of `obj`.