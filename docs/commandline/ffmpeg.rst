Ripping DVD with FFMPEG
=======================


ffmpeg -i concat:VTS_01_0.VOB\|VTS_01_1.VOB\|VTS_01_2.VOB\|VTS_01_3.VOB -vcodec libxvid -qscale 0 ~/my_movie.mp4

Rotate video
------------

Execute::

	ffmpeg -i 2015-01-01\ 00.*mp4 -vf "transpose=1" out.mp4

For the transpose parameter you can pass:

	0 = 90CounterCLockwise and Vertical Flip (default)
	1 = 90Clockwise
	2 = 90CounterClockwise
	3 = 90Clockwise and Vertical Flip


Tips
----

List available codecs::

	ffmpeg -codecs


References
----------
- http://stackoverflow.com/questions/3377300/what-are-all-codecs-supported-by-ffmpeg
- http://blog.desdelinux.net/howtorippear-o-copiar-un-dvd-a-mano-con-cat-y-ffmpeg/ [spanish]
- http://stackoverflow.com/questions/3937387/rotating-videos-with-ffmpeg
