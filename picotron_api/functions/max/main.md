# max(number1, number2)

## Overview
Returns the bigger of two numbers. 

## Arguments

### `number1`: number
An int or a float to be compared with number2

### `number2`: number
An int or a float to be compared with number1

## Returns

### number
The bigger of the two numbers

## Examples

Make sure a value doesn't go below zero, useful for healthbars and bounding boxes.
```lua
player.hp = max( 0, player.hp-1 )
```
