# stop([message])

## Overview

`stop` halts the program and prints a message to the terminal.

This is meant for use during development; unlike [error()](/picotron_api/functions/error/main.md), this simply suspends the program and can be resumed by the terminal with [`resume`](/system/details/util/resume/main.md) if it is the present working cartridge.

## Arguments

### `[message]`: string

A message that is printed to the terminal