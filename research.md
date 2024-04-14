
# Notes on interacting with the accessibility layer from python

[Windows](#windows)
[MacOS](#macos)
[Linux](#linux)


## Windows

- https://stackoverflow.com/questions/55547940/how-to-get-a-list-of-the-name-of-every-open-window


## MacOS

- https://stackoverflow.com/questions/52545917/how-can-i-list-all-open-windows-on-mac-from-a-python-script
	> You can use pyobjc. This should get the title names for you:
	>
	> from AppKit import NSWorkspace
	> [apps["NSApplicationName"] for apps in NSWorkspace.sharedWorkspace().launchedApplications()]
	>
	> A little more background: pyobjc is implemented using Quartz Window Services, which is the program they used to manage application windows on Mac OS.

- https://www.sitepoint.com/quick-tip-controlling-macos-with-python/

- https://stackoverflow.com/questions/72507456/how-can-i-control-a-program-via-apple-accessibility


## Linux

Not sure about this but I think we may have to treat each desktop environment separately? it would be nice if we could find a generic way that works on all desktop environments but that may mean we need to detect for and treat X11 and Wayland separately? Lets see what we can dig up.

### Gnome

- Maybe this work on X11 (doesn't work for Wayland) - https://askubuntu.com/questions/1290436/how-to-get-all-applications-windows-in-the-current-workspace-in-the-view-of-the


Hmmm maybe we need dbus?
- https://stackoverflow.com/questions/45465016/how-do-i-get-the-active-window-on-gnome-wayland
- https://unix.stackexchange.com/questions/203410/how-to-list-all-object-paths-under-a-dbus-service
- https://unix.stackexchange.com/questions/399753/how-to-get-a-list-of-active-windows-when-using-wayland (broken already with gnome 41)


This is making things look hard: https://stackoverflow.com/questions/45762522/get-gdk-window-from-xid-under-wayland


AT-SPI
- https://www.freedesktop.org/wiki/Accessibility/AT-SPI2/
This will work for some apps, the same ones accerciser can see https://www.freedesktop.org/wiki/Accessibility/PyAtSpi2Example/
But sadly not python tkinter apps
- https://stackoverflow.com/questions/40799953/how-to-install-pyatspi


### KDE

Looks like AT-SPI works for newer KDE as well
- https://planet.kde.org/harald-sitter-2022-12-14-selenium-at-spi-gui-testing/
