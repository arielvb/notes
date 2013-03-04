Mac Os X: Command line
======================

List of commands
----------------

Change user shell, with chsh (add or change user database information), next changes to zsh_::

	chsh -s /bin/zsh

.. _zsh: http://www.zsh.org/

Extend Command line tools
-------------------------

brew
+++++


    Homebrew installs the stuff you need that Apple didn’t.

    -- HomeBrew

See: http://mxcl.github.com/homebrew/

gettext
+++++++

Install with brew_::

    brew install gettext

Installs the libraries and the utilities:

    autopoint envsubst gettext gettext.sh gettextize msgattrib msgcat msgcmp msgcomm msgconv msgen msgexec msgfilter msgfmt msggrep msginit msgmerge msgunfmt msguniq ngettext recode-sr-latin xgettext

But doesn't add to your path! You need to modify the env. variable $PATH::

    vi ~/.bash_profile

And add to the end or modify previous declarations::

    export PATH=${PATH}:/usr/local/opt/gettext/bin

grolwnotify
++++++++++

`growlnotify http://growl.info/extras.php#growlnotify` is a command line tool to display notifications from the command line with `Growl`.

For example, lauchn a fake notification from Disk Utility::

	growlnotify -t "Warning" -a Disk\ Utility -m "Replace your disk!"

More interesting is use a custom image icon, with the *--image* parameter::

	growlnotify -t "My App notification" --image icatpy/icat.png  -m "Hello!"

Remove MacOsX custom files from zip
-----------------------------------

To see the contents of a zip file::

    unzip -l filename

To remove zip contents, for example everithing inside __MACOSX::

    zip [filename] -d __MACOSX/*

