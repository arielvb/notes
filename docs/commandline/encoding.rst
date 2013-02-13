Encodings
=========

They are multiple encoding formats for characters, utf-8, machintosh, windows, iso-xxxx-x...

iconv
-----

This program converts text from one encoding to another. It's a comand line program, see **man iconv** for details.

Example::

	 iconv --from-code=UTF-8 --to-code=ISO-8859-1 file.csv >  file.csv
