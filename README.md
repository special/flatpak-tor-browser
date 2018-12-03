# Flatpak sandboxed Tor Browser

This is a simple flatpak install of Tor Browser. Flatpak isn't particularly
security focused, but it has a reasonable application sandbox and it's
definitely an improvement over running an unconfined browser. This is a much
less secure but somewhat more easily maintainable/practical alternative to
the deprecated sandboxed-tor-browser.

Firefox and Tor are currently sandboxed together, meaning Firefox has network
access. Figuring out a way to separate these under flatpak would be a huge
improvement.

To update tor, edit the .json file with a new URL and sha256 and rebuild. The
updater in Tor Browser will not work.

## Notes

start-tor-browser is patched to load firefox profile from $XDG_DATA_HOME,
because /app/ is read-only. Torlauncher sets the tor data directory relative
to the profile path.

There is no wayland support in this firefox, so X11 and DRI are exposed.
Fortunately, all of their vulnerabilities have already been found and fixed.
