Encodings
=========

In a perfect world only one encoding will exist, but that will not be funny.  Dealing with encodings normally is a pain, because the list of encoding formats is too long but the more common are ascii, utf-8, machintosh, windows, iso-xxxx-x.

Some encodings has reduced, or none, support to non english characters like á or ñ. 

Utilities
---------

iconv
+++++

**iconv** converts file from one encoding to another; is a encoding converter.

**iconv** is a comand line program, check program options with  **man iconv** or **iconv --help**; or take a look to the next examples for the most common.

The first example, will convert a file in utf-8 to iso-8859-1 [1]_::

	 iconv --from-code=UTF-8 --to-code=ISO-8859-1 file.csv >  file.csv

.. [1] Microsoft Excel has some issues displaying UTF-8's characters in CSV files, but not with the ISO-8859-1's encoding. 
