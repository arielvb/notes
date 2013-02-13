BlackBerry
==========

Connect via ssh [1]
-------------------

If you have previously configured Eclipse to work with your Blacberry device, you can reuse the existing sshkey.

In Mac OS X you can find it at *~/Library/Research In Motion/* in other OS you can find the exact path in the Eclipse Preferences searching for *BlackBerry Plugin*.

1. Run *blackberry connect*, remenver change the executable path, password and ip before execute::

	
	/Users/arkow/projects/blackberry/blackberry.tools.SDK/bin/blackberry-connect 192.168.1.34 -sshPublicKey "/Users/arkow/Library/Research In Motion/bbt_id_rsa" -password dummypasword


2. Open the *ssh* connection, using *devuser* as username::
	
	ssh devuser@192.168.1.34 -i bbt_id_rsa


.. [1] using eclipse credentials

References
----------

- http://blog.skufel.net/2012/07/how-to-access-blackberry-playbook-via-ssh/
