Pypi
====

Pypi is the *Python* pacakage index, also know as Cheesechop.


Register an account
-------------------

The website allows register an account to upload pacakges. You can login also login using OpenId.

.. note:

	Registering and account isn't needed to browse or download packages.


Register a package
------------------

One you have a package created and before uplooad you must register it::

	python setup.py register


Uploading a package
-------------------

To upload a package you must create a distribution, using *sdist*, *bdist*...

To upload the sdist::

	python setup.py sdist upload

The fast way
------------

	python setup.py register sdist upload

