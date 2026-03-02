# chooser(options, callback)

## Overview
`chooser` opens a filenav process, allowing for the user to select one or more files and folders.

These act as if the files were dragged on top of the process when you select the files.

Files selected with `chooser` are able to be read and written from in sandboxed processes, no matter where they are sourced.

## Arguments

### `options`: string|table|nil

If `options` is a string, it is treated as `{path=options}`, acting as the starting path of the filenav.

When `options` is a table, it can have the following properties (all are optional):

* intention - the intent of the filenav (defaults to "choose_items")
* path - a path to a directory (defaults to "/")
* prompt - the bottom left text in the intention pane
* title - the title of the filenav process
* verb - the verb used in the bottom right in the intention pane

#### `callback`: function|nil

If `callback` is set, it is called when the user finishes their action, calling `callback(msg)`.

If `callback` is nil, it defaults to a generic [drop_items](/picotron_api/events/default_events/drop_items/main.md) event.

## Example

Sourced from the [Picotron Manual](https://www.lexaloffle.com/dl/docs/picotron_manual.html)

Print the selected items
```lua
on_event("drop_items", function(msg) print(pod(msg.items)) end)
chooser()
```

Choose a single file via a menu item by using the "select_file" intention:
```lua
window(240,80)
menuitem{
    id = "select",
    label = "Select File",
    action = function()
        chooser(
        {
            path = "/", -- starting path
            intention = "select_file" 
            -- intention = "save_file_as" -- same but prompt for overwrites
        },
            function(msg) fn = msg.filename end
        )
    end
}

function _draw() 
    cls(7)
    if (fn) print("selected: "..fn, 20,20, 1)
end
```