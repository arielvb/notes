Imagemagick
===========

Creating tiles
--------------

Basic usage::

	convert FILE -crop geometry tiles_%d.jpg

Recomend usage for jpg files, tile + remove exif information::

	convert FILE -crop geometry -strip tiles_%d.jpg

Recovering a copped image, (doesn't work with jpg tiles)::

	convert tiles_*.gif -mosaic recover.gif

.. TODO link to Imagemagick examples -- Cutting and bordering


Creating gifs
-------------

 convert -delay 20 -loop 0 -resize 800x522 *.jpg ../grup.gif
