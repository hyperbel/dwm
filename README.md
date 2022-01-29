# dwm - dynamic window manager
My build of suckless' dynamic window manager (dwm)

## Requirements
In order to build this patch you need the Xlib header files as well as
the xcb header files.

## Installation
Edit config.mk to match your local setup (dwm ist installed into the /usr/local
namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):
	
	`make clean install`

## Running dwm
Add the following line to your xinitrc to startx dwm using startx:
	
	`exec dwm`

In order to connect dwm to a specific display, make sure that the 
DISPLAY environment variable is set correctly, e.g.:

	`DISPLAY=foo.bar:1 exec dwm`

(This will start dwm on display :1 of the host foo:bar.)

In order to display status ifo in the bar, you can do something
like this in your .xinitrc:

```
	while xsetroot -name "date uptime | sed 's/.*,//'"
	do
		sleep 1
	done &
	exec dwm

```

## Configuration
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.
