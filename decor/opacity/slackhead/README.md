## Scripts to give opacity features to WMs that don't support it.
---

Required:

* A composite manager such as compton or xcompmgr
* xdotool
* wmctrl

Opacity data is stored in ~/.xopacity<br />
The file is read by the 'opacity' script and settings are applied to
all existing windows that are contained in that file.

Note that I have only tested this with compton.<br />
Compton should be started by:<br />
dbus-launch compton (options) &<br />
or eg in ~/.config/i3/config by:<br />
exec --no-startup-id dbus-launch compton (options)<br />

Note also that some windows refuse to have their opacity changed.

Configuration for i3:<br />

```
# Opacity stuff for i3

# Give windows the _NET_WM_WINDOW_OPACITY atom at startup.
# This command should be at the END of you startup file
# or at the END of ~/.config/13/config:
exec --no-startup-id ~/scripts/opacity

# Suggested keybinds:

# Use this bind if you have restarted i3 and opacity is no longer working:
bindsym $mod+o exec --no-startup-id ~/scripts/opacity

# Give full opacity to the focused window:
bindsym  $mod+f exec --no-startup-id ~/scripts/fullopacity

# Increase opacity in the focused window ($mod+]):
bindcode $mod+35 exec --no-startup-id ~/scripts/incopacity

# Decrease opacity in the focused window ($mod+[):
bindcode $mod+34 exec --no-startup-id ~/scripts/decopacity
```
