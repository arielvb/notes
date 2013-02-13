Python for apache
=================


Installation
------------


Mac Os X
^^^^^^^^

#. Install mod_wsgi using *brew*::

	brew update
	brew install mod_wsgi

#. Edit the /etc/apache2/http.conf and add::

	LoadModule wsgi_module /usr/local/Cellar/mod_wsgi/3.3/libexec/mod_wsgi.so


.. note::
	
	The exact path for mod_wsgi can be found with::
		brew list mod_wsgi


wsgi frameworks
---------------


References
----------

- http://stackoverflow.com/questions/4341769/how-can-i-get-mod-wsgi-working-on-mac
- Flask Deployment Documentation, http://flask.pocoo.org/docs/deploying/mod_wsgi/
