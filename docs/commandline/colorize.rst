Colorize
--------

The command line with colors looks so pretty!

grep
....

Use the argument *--color*::

	grep --color=auto

The options are:
	
	- auto: doesn't colorize if the output is a pipe.
	- always
	- never

less / more
...........

Use the argument *-R* (or *-r*)::

	more -r

Example colorize grep output::

	rgrep --color=auto TODO . | more -r
	

pygmentize
..........

pygmentize colorizes the input allowing different lexers::

	pygmentize [-l lexer] [file]

The lexer will be autodected, but if not some of the lexers are:

	- rst: reStructuredText
	- html
	- python
