# btn([b],[p])

## Overview

Returns the state of button `b` for player index `p` (default `0`; being Player 1).

For the state of keys, see [key()](/picotron_api/functions/key/main.md)

For button presses, see [btnp()](/picotron_api/functions/btnp/main.md)

## Arguments

### `[b]`: number

The button state you are querying

#### 0,1,2,3
LEFT, RIGHT, UP, DOWN

This is equivalent to the inputs on joystick 1 / dpad 1.

This is equivalent to the arrow keys on a keyboard.

#### 4
O

This is one of the face buttons of the controller; being the bottom face button.

Equivalent to `Z` on a keyboard.

#### 5
X

This is one of the face buttons of the controller; being the left face button.

Equivalent to `X` on a keyboard.

#### 6

Menu button

Equivalent to `ENTER` on a keyboard.

#### 8,9,10,11
LEFT, RIGHT, UP, DOWN

This is equivalent to the inputs on joystick 2 / dpad 2.

This is equivalent to `WASD` on a keyboard.

#### 12
Unnamed

This is one of the face buttons of the controller; being the top face button.

This is equivalent to `F` on a keyboard.

#### 13
Unnamed

This is one of the face buttons of the controller; being the right face button.

This is equivalent to `G` on a keyboard.

#### 14
Left Bumper

This is equivalent to `Q` on a keyboard.

#### 15
Right Bumper

This is equivalent to `E` on a keyboard.

## `[p]`: integer

`[p]` is the player index (`0..15`); each being a different controller. This defaults to `0` (player 1).

Both the keyboard and the first controller to connect takes up player 1 (index 0).

## Returns

### `state`: number|boolean

#### Non joystick inputs

Returns `false` when not down, `true` when down.

#### Joystick values

Returns `false` when the joystick is in the deadzone or not moved.
It is impossible for e.g. LEFT and RIGHT to be held at the same time. To get raw controller values, use

```lua
peek(0x5400 + 
player_index*16 + button_index).
```

## Examples

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

Fetching the x axis of the primary stick (stick 1)
```lua
local dx = (btn(1) or 0) - (btn(0) or 0)
```