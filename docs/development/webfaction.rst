Webfaction
==========

Crea lloc web
-------------

Cal crear un website: dominis (domini + www.domini), aplicacio, usuaris (opcional).

https
+++++

S'ha de crear tant la versió http com https (2 websites) amb la mateixa aplicació (o no) i els mateixes dominis


Crear usuari
------------

1. Des de la web crear un usuari amb access a consola, més tard restringirem l'accès per a que només pugui accedir per ftp.

2. Crear la carpeta de l'aplicacio.

3. Afegir permisos d'excucio al directori de l'usuari principal al nou usuari::
   setfacl -m u:[usuari]:--x $HOME
4. Afegir permisos al directori concret::
   setfacl -m u:[usuari]:--x $HOME/[directori]


Git
---

Anar a la carpeta repos de l'aplicació on està instal·lat git::
    cd webapps/gitpxc/repos

    git init --bare {repo}.git
    cd {repo}.git
    git config http.receivepack true

Editar la descripció del projecte::

    vi description

Definir els autors afegir al fitxer config::

    [gitweb]
        owner = Ariel

A la nostra màquina dins de la carpeta que volem afegir al repositori::

    git init
    touch README
    git add README
    git commit -m "First commit"
    git remote add origin https://dev.arielvb.com/git/{repo}.git
    git push origin master


mod_wsgi i AuthUserFile
-----------------------

Per protegir directoris dins d'una aplicació amb mod_wsgi cal carregar els moduls d'Apache corresponents, ja que per defecte es carreguen.

Cal editar el fitxer apache2/conf/http.conf i afegir::

	LoadModule auth_basic_module modules/mod_auth_basic.so
	LoadModule authn_file_module modules/mod_authn_file.so
	LoadModule authz_user_module modules/mod_authz_user.so

Si volem protegir totes les rutes cal afegir al bloc **directory**::

	AuthUserFile [ruta al fitxer htpasswd]
	AuthName "[Text a mostrar a la finestra de carrega]"
    	AuthType Basic
    	require valid-user

Si només volem protegir una part de la aplicació cal crear un nou bloc::
	
	<Location [ruta]>
	        AuthUserFile [ruta al fitxer htpasswd]
	        AuthName "[Text a mostrar a la finestra de carrega]"
	        AuthType Basic
	        require valid-user
	</Location>
	


Referencies
-----------
- http://docs.webfaction.com/software/git.html
- http://docs.webfaction.com/software/general.html#granting-access-to-specific-users
- http://community.webfaction.com/questions/256/apache-basic-authentication-for-mod_wsgi-inc-django-applications
- http://flask.pocoo.org/snippets/65/
