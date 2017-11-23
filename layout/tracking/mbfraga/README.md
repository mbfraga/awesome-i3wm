# tracki3

Track the current i3layout by printing a nicely formatted tree. The goal is for
this to serve as a didactic tool for new users, and also to help more seasoned
users troubleshoot problems and understand more advanced behaviors.

Dependencies:

* i3ipc-python


## Usage

Without options, tracki3 will print the layout tree once.

In order to have tracki3 update periodically in order to track the i3 layout
as you spawn and move containers, you have to run it with the following
options:

`tracki3 -t -d 1`

The **-t** option will enable the tracking mode, while the **-d** option sets
the interval.


## Other Examples

To have the tree display without colors, use:

`tracki3 -tc -d 1`

To only show output and workspaces (no information on containers), run:

`tracki3 -t -d 1 --only-workspaces`

For more command line options, run:

`tracki3 -h`
