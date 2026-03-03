# btnp([b],[p])

## Overview

Returns the pressed status of button `b` for player index `p` (default `0`; being Player 1).

`btnp` is short for "Button Pressed"; only returning `true` when a button is down and was not down the last frame.

This also repeats every 30 frames; returning true every 8 frames after that.

This is typically used in menus or grid-based player movement.

The state that btnp() reads is reset at the start of each call to [_update()](/picotron_api/program_structure/main.md), so it is preferable to use btnp only from inside that call and not from [_draw()](/picotron_api/program_structure/main.md), which might be called less frequently.

Custom delays (in frames) can be set by poking the following memory addresses:

```lua
poke(0x5f5c, delay) -- set the initial delay before repeating. 255 means never repeat.
poke(0x5f5d, delay) -- set the repeating delay.
```

`0` can be used for the default behaviour (delays `30` and `8`)

For key presses, see [keyp()](/picotron_api/functions/keyp/main.md)

For button states, see [btnp()](/picotron_api/functions/btnp/main.md)

## Arguments

### `[b]`: number

The button you are querying

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

### `pressed`: number|boolean

#### Non joystick inputs

Returns `false` when unpressed, `true` when pressed.

#### Joystick values

Returns `false` when the joystick is in the deadzone or not moved.

Each joystick button index (e.g: 0,1,2,3 or 8,9,10,11) returns a value from `0..255`; being how far the joystick is oin that direction. If a DPAD or keyboard is used; this can only be `0` or `255`.

Joystick values are processed so that the return values are only physically possible positions of a circular stick; the magnitude is clamped to 1.0 (right + down) even with digital buttons gives values of 181 for btn(1) and btn(3).

It is impossible for e.g. LEFT and RIGHT to be held at the same time. To get raw controller values, use

```lua
peek(0x5400 + 
player_index*16 + button_index).
```