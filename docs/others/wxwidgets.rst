wxwidgets
=========

:Website: http://wxwidgets.org

Installation
------------

Mac OS X
++++++++

Install wxwidgets under Mac OS is really easy with **brew**; but it takes some time because homebrew compiles wxwidgets before installing the python bindings.

Once is installed you must modify the PYTHONPATH enviroment variable to point to the installation path, something like that::

	export PYTHONPATH=/usr/local/Cellar/wxmac/2.9.4.0/lib/python2.7/site-packages/wx-2.9.4-osx_cocoa:$PYTHONPATH

A good place to add this line is in your ~/.bash_profile

Python Bindings
---------------

At the of wxpython.org you will find an `example <http://wiki.wxpython.org/Using%20wxPython%20Demo%20Code>` to test if everithing has been installed correctly.

A full package of demos are avaible for download at: http://wxpython.org/download.php#demo


.. note:: 

	The demo application bundle for mac, doesn't work if you have installed wxwidgets with homebrew.

