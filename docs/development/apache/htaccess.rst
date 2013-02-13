htaccess: Tips
==============

Redirigir http a https
----------------------

Requisito: modRewrite

Crear un fichero .htaccess y introducir el siguiente bloque de reglas::

	RewriteEngine On
	RewriteCond %{HTTP:X-Forwarded-SSL} !on
	RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [R,L]


Proteger con usuario y contraseña
+++++++++++++++++++++++++++++++++

Requisito: 

AuthUserFile [RUTA AL FICHERO DE AUTENTIFICACIÓN]
AuthName "[TEXTO IDENTIFICATIVO SITIO]"
AuthType Basic
require valid-user

.. warning:: 
	
	La ruta del fichero de autentificación ha de ser absoluta