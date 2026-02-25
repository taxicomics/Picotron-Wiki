# on_event(event, function)

## Overview

`on_event` allows for you to subscribe to the event `event` and act with function `function` upon the event.

You can subscribe to the same event multiple times.

## Arguments

### `event`: string

The event to listen to, this can be any arbritrary value, but there are some default events as listed below.

### `function`: function|nil

This function is called upon the event, when `nil` it removes all subscriptions to the event.
It is called with a `msg` table, consisting of data to do with the event. Detailed event information is found [here](/picotron_api/events/readme.md)