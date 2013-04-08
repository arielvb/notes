Firefox
=======

Pàgines especials
-----------------

No totes les opcions de Firefox estàn accesibles des de les opcions dels menus. Algunes només es pot accedir escribint una adreça concreta a la barra de navegació i algunes de les opcions del menu tenen un accés també des de aquesta:

- `about:home` la pàgina definida com predeterminada.
- `about:addons` per accedir a la finestra de complements.
- `about:memory` informació sobre la gestió de memòria.
- `about:support` informació sobre la configuració tecnica del navegador.
- `about:config` consulta i modificació de paràmetres configurables del navegador i complements.

Ubuntu - Instal·lació des de els repositoris de Mozilla
-------------------------------------------------------


#. Afegir repositori i instal·lar firefox::

        sudo add-apt-repository ppa:mozillateam/firefox-stable
        sudo apt-get update
        sudo apt-get upgrade

#. Instal·lar paquet d'idioma català, canviar *ca* per *es* si es vol castellà::

        sudo apt-get install firefox-locale-ca


#. Arrancar Firefox i escriure a la barra de navegació::

        about:addons

#. Clicar a l'icona d'eines i triar l'opció *Check for updates / Comprova si hi ha actualitzacions*

#. Reiniciar Firefox.


Complements
-----------

Url: **about:addons**

Llista de complements intersants:

:Firebug: Per a tots aquells que creen webs i aquells que fan web-scrapping:)
:Web Developer: barra d'eines per desenvolupadors, permet desactivar la memòria cau del navegador, javascript...
:Pearl Crescent Page Saver: permet desar pàgina sencera, o la part visible, com imatge.
:JSONView: visualitza les respostes JSON en colors i amb format directament al navegador [by laura.p]
:httpsEveryWhere: activa la navegació per https a una serie de llocs web on no ho està de forma predeterminada.
:adblock plus: bloqueja els anuncis de les pàgines web. Per que una navegació sense publicitat no té preu.


Modify about:home search engine
-------------------------------

Modify the key **search-engine** in the chromeappstore.sqlite inside your profile.

Default value in firefox-beta 17 is::

	> sqlite3 chromeappsstore.sqlite "SELECT * FROM webappsstore2 WHERE key='search-engine';"

	emoh.:moz-safe-about|search-engine|{"name":"Google","searchUrl":"https://www.google.com/search?q=_searchTerms_&ie=utf-8&oe=utf-8&aq=t&rls=org.mozilla:es-ES:official&client=firefox-beta"}|0|

To set duckduckgo as search engine::

	sqlite3 chromeappsstore.sqlite 'UPDATE webappsstore2 SET value=\'{"name":"DuckDuckGo","searchUrl":"https://duckduckgo.com/?q=_searchTerms_"}\' WHERE key="search-engine";'

The easy way, in the about:home page, paste in the url field::

	javascript:{localStorage["search-engine"]="{\"name\":\"Google\",\"searchUrl\":\"http://www.google.com/search?q=_searchTerms_&ie=utf-8&oe=utf-8&aq=t&rls=org.mozilla:en-US:official&client=firefox-a\"}";void(0);}


.. TODO backup command

	#Backup
	{"name":"Google","searchUrl":"https://www.google.com/search?q=_searchTerms_&ie=utf-8&oe=utf-8&aq=t&rls=org.mozilla:es-ES:official&client=firefox-beta"}

References
----------

- http://support.mozilla.org/ca/questions/779082 (2012-10-28)
