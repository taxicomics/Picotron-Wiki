# input([prompt],[flags])

## Overview

`input` is used to allow terminal programs to be interactive; this is a blocking function and stalls the program until the user enters a response.

The response of the user is returned.

Interactive terminal programs that run indefinitely do not have a [_update](/picotron_api/program_structure/main.md) or [_draw](/picotron_api/program_structure/main.md) callback, and instead can use input() in the mainloop.


Note that there is currently no way to respond to non-textinput keys (like cursors) from terminal programs.

Terminal programs can be run during development with ctrl-r, but as they occupy the same process as the terminal that is displaying them; there may be some disparities in behaviour.

## Arguments

### `[prompt]`: string

The string that shows to the left of the user's input, default: "?"

### `[flags]`: bitfield

A bitfield that can change how inputs work.

Available flags:

* 0x1 hide the prompt once input() has returned
* 0x2 complete the input when a single character is given (do not wait for enter)
* 0x4 do not block -- return nil when there is no response that frame

## Returns

### `response`: string

The user's response to the input

## Example

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

```lua
print("press k,l to adjust value or q to quit")
print("") -- is going to get consumed by \r below
val = 10
while true do
    res = input("",0x7)
    if (res == "q") exit()
    if (res == "k") val -= 1
    if (res == "l") val += 1
    print("\rvalue: "..val) -- \r to write over previous line
end
print("finished")
```