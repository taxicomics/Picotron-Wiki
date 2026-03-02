# type(value): string

## Overview

`type` returns the type of a value in the form of a string.

For whether a number is an `integer` or a `float`, make use of `math.type(num)`.

## Arguments

### value

The value to query the type of

## Returns

### `type`: string

The type of the value `value`, possibilities being:

* string (`"hello world"`)
* number (`2`)
* function (`print`)
* boolean (`true`)
* nil (`nil`)
* table (`{}`)
* userdata
* thread