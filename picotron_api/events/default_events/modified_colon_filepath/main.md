# modified:filepath

## Overview

You can detect modifications to a filepath through the filepath, prefixed by `modified:`, e.g: detecting changes to `/foo.txt`, `modified:/foo.txt`

Sandboxed programs can only subscribe to changes in `/ram/shared` and `/appdata`.

## `msg` properties

### filename

Filename of the filepath.