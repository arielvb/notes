Python Freezers
===============

.. TODO writte an introduction and look for more alternatives

- py2app_
- pyinstaller_


py2app
------

Phonon (qt)
+++++++++++

Once the application is freezed, the phonon engine could'nt be initiated.


Pyinstaller
-----------

Mac
+++

PyInstaller has some issues creating Mac Os X bundles:

- No application icon support.
- If our application uses Qt, it forgets to add the qt_menu.nib file.


References
----------

- http://tech.xster.net/tips/deploy-pyqt-applications-on-mac-os-x-with-pyinstaller/
