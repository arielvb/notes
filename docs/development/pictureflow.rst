PictureFlow
===========

PictureFlow is a Coverflow widget for Qt, it was developed by Ariya.

..warning::

    **Pictureflow (python) loves memory** usage.
    250 images => 1.62 GB of RAM
    50 images => 538 MB of RAM

    **Pictureflow (cpp) also loves memory**
    250 images => 1.39 GB of RAM
    50 images (not the same pack as in python) => 99 MB of RAM

Resize images
-------------

Before call pictureflow you must created a resized version of your images, or tu much memory will be allocated!

You can resize faster with imagemagick, for exemple to resize all the jpg in your folder using *bash* and *convert*::

    for i in `ls *.jpg`; do convert -sample 512x512 $i 512_$i; done

This will make that PictureFlow only uses **225 MB of RAM** for 250 images.


Build
-----

#. Donwload last version of pictureflow from the github repository of Ariya::

    git clone https://github.com/ariya/pictureflow.git

.. TODO git clone uri

#. Run go to *pyctureflow-qt/pyqt/lib* and run::


    qmake
    make install

#. If *make install* donsn't copy anything, copy pictureflow lib (pictureflow.a) to::

    /Applications/QtSDK/Desktop/Qt/4.8.1/gcc/lib

#. Go to pyqt folter, one level up and run (better step by step)::

    python configure.py
    make
    make install

#. Edit the demo.py file to add your image path, and run it with python.


Other references
----------------

PictureFlow - listing images in PyQt4 http://www.rkblog.rk.edu.pl/w/p/pictureflow-listing-images-pyqt4/

The Calibre plugin pictureflow.

