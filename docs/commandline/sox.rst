SoX - Sound eXchange
====================

SoX_ **the sound utility**!

:Website: http://sox.sourceforge.net/
:Category: audio, convert, cmd, nogui

Installation
------------

.. note::

	SoX by default doesn't have mp3 encoding support, to prevent legal issues
	with the *mp3* patents. 
	Some third pary packages/libraries permits you bypass that problem.


Linux
+++++

First check if SoX_ is avaible on your packagemanager, and check if that version is up to date, if the version is too old; consider download SoX_ from `their website <https://sourceforge.net/projects/sox/files/sox/>`_ and build it from source.

Ubuntu 12.04
~~~~~~~~~~~~~

.. note::
	To install sox quick with mp3 support run: 
		sudo apt-get install sox libsox-fmt-mp3

	If you wan't to install SoX only or know about the extra packages continue reading.

1. Install using the repository version of SoX_::

	sudo apt-get install sox

2. Enable mp3 encoder::

	sudo apt-get install sox libsox-fmt-mp3

Mac OS X
~~~~~~~~

SoX_ can be installed using homebrew, first check the build options with::

	brew info sox

The diferents options extends the default behaviour with some extra encoders 
(conversion formats), check the end of this section to know what are the diferents options.

To build without extensions (without mp3, ogg conversion)::
	
	brew install sox

One of the extra encoders is provided by *libvorbis*, offering encoding file as ogg, to isntall this incoder you must have not installed SoX_ and run::

	brew install sox --with-libvorbis

.. TODO: mp3 encoder support?


Usage
-----

SoX is really easy to use, if you know how to use a commandline program. Take a look to the next examples, and you will discover some of the features of SoX_.

#. Play an audio file::

	play filename

#. Convert an mp3 to ogg (the output format is autodected using the new file extension)::

	sox filename newfile.ogg


Advanced usage
++++++++++++++

#. Create spectrogram::

        sox casa.mp3 -n spectrogram

#. Tunning spectrogram example params::

        sox casa.mp3 -n spectrogram -Y 130 -l - casa_spec.png

#. Reverse sound track::

        sox casa.mp3 reverse asac.mp3

.. TODO: creating a waveform using the SoX's option -plot and gnuplot or octave

Some interesting resources
--------------------------


- Sox Documentation: http://sox.sourceforge.net/sox.html
- Building sox with mp3 support on Mac: http://ggkarman.de/tech/building-sox-with-mp3-support-on-osx/

.. _SoX : http://sox.sourceforge.net/
