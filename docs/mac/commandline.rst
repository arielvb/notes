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


Remove MacOsX custom files from zip
-----------------------------------

To see the contents of a zip file::

    unzip -l filename

To remove zip contents, for example everithing inside __MACOSX::

    zip [filename] -d __MACOSX/*

