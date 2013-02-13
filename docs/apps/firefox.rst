Firefox
=======

Instal·lació des de els repositoris de Mozilla
----------------------------------------------


#. Afegir repositori i instal·lar firefox::

        sudo add-apt-repository ppa:mozillateam/firefox-stable
        sudo apt-get update
        sudo apt-get upgrade

#. Instal·lar paquet d'idioma català, canviar *ca* per *es* si es vol castellà::

        sudo apt-get install firefox-locale-ca


#. Arrancar Firefox i escriure a la barra de navegació::

        about:addons

#. Clicar a l'icona d'eines i triar l'opció *Check for updates / Comprova si hi ha actualitzacions*

#. Reiniciar firefox.


Complements
-----------

**about:addons**

Llista de complements intersants:

:Firebug: :)
:Web Developer: barra d'eines per desenvolupadors
:Pearl Crescent Page Saver: permet desar pàgina sencera (o no) com imatge (impr pant++)
:JSONView: visualitza les respostes JSON en colors i amb format directament al navegador [by laura.p]

Modify about:home search engine
-------------------------------

Modify the key **search-engine** in the chromeappstore.sqlite of your profile.

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
