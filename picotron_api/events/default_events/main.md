# Default Events

## `modified:filepath`

You can detect modifications to a filepath through the filepath, prefixed by `modified:`, e.g: detecting changes to `/foo.txt`, `modified:/foo.txt`

Sandboxed programs can only subscribe to changes in `/ram/shared` and `/appdata`.

The following information is given through the `msg` table:

### filename

Filename of the filepath.

## `move`

Called when the window is moved

The following information is given through the `msg` table:

### win_x

x-position of the window

### win_y

y-position of the window

## `resize`

Called when the window is resized

The following information is given through the `msg` table:

### width

Width (px) of the window

### height

Height (px) of the window

### [x]

The x-position of the window is sometimes sent through this.

### [y]

The y-position of the window is sometimes sent through this.

## `grab`

Used when a window requested that it is grabbed.

## `drag_toolbar`

Used to change the toolbar's y-position.

The `msg` table has the following properties:

### dy

The y-position to drag the toolbar to

## `drag_infobar`

Used to change the infobar's y-position.

The `msg` table has the following properties:

### dy

The y-position to drag the infobar to

## `dock_toolbar`

Used to choose whether the toolbar is docked.

The `msg` table has the following properties:

### state

A boolean of whether the toolbar is docked, true, or the toolbar is undocked, false.

## `bring_window_to_front`

Typically unused by cartridges, instead handled by `events.lua`.

Used by the toolbar to bring the window to the front.

## `resume_pwc`

Typically unused by cartridges, instead handled by `events.lua`.

Used when the present working cartridge is resumed.

## `drop_items`

Called when items/files are dropped onto the window.

This can also be triggered with pasting item data through `CTRL+V`.

The following information is given through the `msg` table:

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

## `gained_visibility`

Called when a process gains visibility.

## `lost_visibility`

Called when a process loses visibility.

## `filenav_refresh`

Called by the system `about.p64` when icons are updated to trigger the filenav to refresh icons.

## `lost_focus`

Called when a process loses its focus.

## `gained_focus`

Called when a process gains its focus.

## `confirm_close_window`

Placeholder event used to do something when window is closed, discarding

It is marked to not used this event by zep.


```
-- unsaved changes. ** don't use this event
-- design will likely be reworked **
```

## `squash`

Typically unused by cartridges, instead handled by `events.lua`.

Called when a window is resized as a result of squashing.

## `menu_action`

Called when a menuitem is acted upon, you shouldn't have to use this as it is handled automatically with menuitems.

## `update_menu_labels`

Called when the pause menu is brought up, requested by the window manager.

You shouldn't have to use this as it is handled automatically with menuitems.

## `toggle_pause_menu`

Typically unused by cartridges, instead handled by `events.lua`.

Called to toggle the pause menu.

## `close_pause_menu`

Typically unused by cartridges, instead handled by `events.lua`.

Called to close the pause menu.

## `toggle_app_menu`

Typically unused by cartridges, instead handled by `events.lua`.

Called to toggle the app menu.

The `msg` table contains the properties:

### context

Unknown

Can be `nil`, `extra` or `floating`, `floating` seems to be legacy and unused.

### proc_id

The process id of the app menu to be toggled.

### x

Unknown

### y

Unknown

## `input_response`

Typically unused by cartridges, instead handled by `events.lua`.

Unknown

## `mouse`

Typically unused by cartridges, instead handled by `events.lua`.

Called when the mouse data is changed. It contains the following properties in the `msg` table:

### mx

x-position of the mouse

### my

y-position of the mouse

### mb

bitfield of the mouse's button presses

## `mousefield`

Typically unused by cartridges, instead handled by `events.lua`.

Similar to the `mouse` event, this is called when the mouse's scrollwheel is updated.

It has the following properties:

### wheel_x

The change in the mousewheel on the x-axis.

`nil` when unchanged.

### wheel_y

The change in the mousewheel on the y-axis.

`nil` when unchanged.

## `mouselockedmove`

Similar to the `mouse` event, this is called when the mouse is moved when the mouse is locked.

It has the following properties:

### locked_dx

The change in the mouse position on the x-axis.

`nil` when unchanged.

### locked_dy

The change in the mouse position on the y-axis.

`nil` when unchanged.

## `keydown`

Typically unused by cartridges, instead handled by `events.lua`.

Called when a key is down.

The `msg` table contains the property:

### scancode

Scancode of the key that is down.

## `keyup`

Typically unused by cartridges, instead handled by `events.lua`.

Called when a key is released/up.

The `msg` table contains the property:

### scancode

Scancode of the key that is up.

## `keydown_ctrl`

Typically unused by cartridges, instead handled by `events.lua`.

Used for carrying over the `ctrl` key's pressed status over different processes.

## `keydown_ctrl_v`

Typically unused by cartridges, instead handled by `events.lua`.

Used for web exports, called when CTRL-V is pressed.

## `clear_key`

Used by `wm` to stop keypresses getting through

The `msg` table contains the property:

### scancode

Scancode of the key that is to be cleared.

## `reset_kbd`

Typically unused by cartridges, instead handled by `events.lua`.

Used when a process is being told to reset its keyboard state.

## `reset_kbd_for_paste`

Typically unused by cartridges, instead handled by `events.lua`.

Used when a process is being told to clear its keypress of `v`.

## `textinput`

Typically unused by cartridges, instead handled by `events.lua`.

Used when text is inputted.

The `msg` table contains the property:

### text

The text that is inputted.

## `exit`

Typically unused by cartridges, instead handled by `events.lua`.

Placeholder event used when confirming window close from system app `confirm.p64`

## `pause`

Called when the process is paused.

## `unpause`

Called when the process is unpaused.

## `extend_fileview`

Used by system apps to request access to particular files.

Requires the process to be a trusted system app (in `/system`, e.g: filenav)

The `msg` table contains the property:

### filename

The requested path, a string, of the file being requested to have access to.

## `search`

Used to set the search term after jumping to the window via ctrl-h

The `msg` table contains the property:

### term

The search term.

## `save_working_cart_files_completed`

Unknown

## `save`

Invoked directly from app menu, and by wm when about to run / save cartridge

The `msg` table contains the properties:

### autosave

A boolean on whether the save is triggered by an auto-save.

### notify_on_complete

A PID of a process to return the finished status of the save event.

## `open_file`

Called by filenav intention.

The `msg` table contains the property:

### filename

Path to the file that is opened.

## `jump_to_spot`

Typically unused by cartridges, instead handled by `events.lua`.

Unknown

The `msg` table contains the properties:

### hloc

Unknown

### extra

Unknown

## `save_file_as`

Called by filenav intention.

The `msg` table contains the property:

### filename

Path to the location of the file to be stored at.

## `update`

Unknown


