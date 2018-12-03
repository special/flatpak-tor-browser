start-tor-browser is patched to load firefox profile from $XDG_DATA_HOME,
because /app/ is read-only. Torlauncher sets the tor data directory relative
to the profile path.

There is no wayland support in this firefox.

It's a shame that firefox has network access. Wonder if it's possible to split
away the tor somehow.

File save dialog is currently broken. Not quite sure why.
