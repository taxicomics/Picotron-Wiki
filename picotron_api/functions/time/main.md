# time(): number
# t(): number

## Overview

`time` returns the amount of seconds since the process has started running. This can become inaccurate as it is relative to `_update`, so if the process lags; the time may be incorrect.

You can make use of [stat(86)](/picotron_api/functions/stat/main.md) for an accurate timestamp which can be compared with the starting timestamp of the program.

## Returns

### `time`: number

The time since the process has started running, relative to the process's update cycle.