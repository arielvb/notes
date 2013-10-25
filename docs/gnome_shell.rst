Gnome Shell
===========

Launchers
---------

To create a launcher for a custom application, you must create a .desktop file under `/usr/share/applications`, `~/.local/share/applications` or `~/Desktop`

As an example the next launcher is for Blender::

	[Desktop Entry]
	Encoding=UTF-8
	Name=Blender
	Exec=/path/to/blender/executable
	Icon=/path/to/blender/icon
	Type=Application
	Categories=Graphics;


References
----------

- Desktop Files (Gnome): https://developer.gnome.org/integration-guide/stable/desktop-files.html.en
- Freedesktop Categories: http://standards.freedesktop.org/menu-spec/latest/apa.html
