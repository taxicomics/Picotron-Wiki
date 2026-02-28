# drop_items

## Overview

Called when items/files are dropped onto the window.

This can also be triggered with pasting item data through `CTRL+V`.

## `msg` properties

### items

The items, a table, dropped onto the window.

The item can contain the metadata of a file, but also follows the structure where an item *can* consist of:

#### mx

The mouse's x-position at the time of dropping the item.

#### my

The mouse's y-position at the time of dropping the item.

#### pod_type

This describes the type of the pod, for files/file locations, this is seen as `location`.

#### location

This is seen with dragging items which are files/locations. This is a string which is the filepath to the file.

#### args

Unknown, stored when creating `.loc` files with the system filenav.

#### env

Unknown, stored when creating `.loc` files with the system filenav.

*Presumably something that is appended to the data received in [env()](/picotron_api/functions/env/main.md).*