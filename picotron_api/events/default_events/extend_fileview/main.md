# `extend_fileview`

Used by system apps to request access to particular files.

Requires the process to be a trusted system app (in `/system`, e.g: filenav)

## `msg` properties

### filename

The requested path, a string, of the file being requested to have access to.