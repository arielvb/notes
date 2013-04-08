mcrypt for Mac and PHP
======================

:Website: http://mcrypt.sourceforge.net/
:Tags: software, mac, php, magento

Mac OS comes with Apache and PHP installed, but maybe you need some extensions that doesn't come with the default installation.

If you need `mcrypt` you have to options `reinstall PHP on Mac OS X <http://justinhileman.info/article/reinstalling-php-on-mac-os-x/>`_ installation with a new version using `homebrew` or install only the extensions you need.

.. note::

     This instrucctions are for Mac OS X 10.6

Requeriments
------------

- XCode

Installing mcrypt
-----------------

To install the mcrypt extension for PHP, first you need to install mcrypt and once installed you need to compile the extension for your PHP version.


The installation mcrypt, you need to compile the source code or install it with `homebrew`::

    brew install mcrypt

.. warning::

    If the default formula doesn't work you can try with a diferent one, check out the section `Custom brew formula`_.



The next step is build the PHP extension for your PHP version. First you need to know the PHP version of your Mac::

    php -v

And then downlad the source code of the same PHP version, in my case 5.3.15, from php.net or using the spanish mirror::

    wget http://es1.php.net/distributions/php-5.3.15.tar.bz2

.. note:

    If you don't have wget, open the URI with your browser.

Extract the source code::

    tar -xf php-5.3.15.tar.bz2

And go to the mcryp extension diretory::

    cd php-5.3-15/ext/mcryp

Prepare the extension to compile::

    phpize

And execute the next oneliner::

    MACOSX_DEPLOYMENT_TARGET=10.6 CFLAGS='-O3 -fno-common -arch i386 -arch x86_64' LDFLAGS='-O3 -arch i386 -arch x86_64' CXXFLAGS='-O3 -fno-common -arch i386 -arch x86_64' ./configure --with-php-config=/Developer/SDKs/MacOSX10.6.sdk/usr/bin/php-config; make -j6;

If the oneliner ends without any error, install the extension::

    sudo make install

The most probable error is related with PHP_FE_END or ZEND_MOD_END. To fix this you must edit the `ext/mcrypt/mcrypt.` and add at the begginning of the file, the definition of both::

    #define PHP_FE_END {NULL,NULL,NULL}
    #define ZEND_MOD_END {NULL,NULL,NULL,0}

Then you must exectute the onliner and the install instruction.

Now you have everithing installed, but your PHP installation doesn't know that mcrypt is avaible; to activate this extension you need to edit the `/etc/php.ini` file adding the next line::

    extension=mcrypt.so

.. note::

        If this file doesn't exists you will find a php.ini.default in the same folder; create a copy of it as php.ini

And check that the extension is correctly installed::

    php --info | grep mcrypt

Finally restart Apache::

    sudo apachectl restart

Custom brew formula
+++++++++++++++++++

Replace the file `/usr/local/Library/Formula/mcrypt.rb` with::

      require 'formula'

      class Mcrypt < Formula
        homepage 'http://mcrypt.sourceforge.net'
        url 'http://sourceforge.net/projects/mcrypt/files/Libmcrypt/2.5.8/libmcrypt-2.5.8.tar.gz'
        sha1 '9a426532e9087dd7737aabccff8b91abf9151a7a'

        option :universal

        def install
          ENV.universal_binary if build.universal?
          system "MACOSX_DEPLOYMENT_TARGET=10.6 CFLAGS='-O3 -fno-common -arch i386 -arch x86_64' LDFLAGS='-O3 -arch i386 -arch x86_64' CXXFLAGS='-O3 -fno-common -arch i386 -arch x86_64' ./configure --disable-dependency-tracking --prefix=#{prefix} --mandir=#{man}"
          system "make -j6"
          system "make install"
        end
      end

References
----------
http://blog.rogeriopvl.com/archives/php-mcrypt-in-snow-leopard-with-homebrew/

Installation log
----------------

The installation fast notes::

  PHP_VERSION="5.3.15"
  # or using bash replace
  a=`php -v`;
  PHP_VESRION=${a:4:6}
  brew install mcrypt
  wget http://es1.php.net/distributions/php-$PHP_VERSION.tar.bz2
  tar -xf php-$PHP_VERSION.tar.bz2
  cd php-$PHP_VERSION/ext/mcryp
  echo "copy next lines into ext/mcrypt/mcrypt.c"
  echo "############################"
  cat << EOF
  #define PHP_FE_END {NULL,NULL,NULL}
  #define ZEND_MOD_END {NULL,NULL,NULL,0}
  EOF
  echo "############################"
  phpize
  MACOSX_DEPLOYMENT_TARGET=10.6 CFLAGS='-O3 -fno-common -arch i386 -arch x86_64' LDFLAGS='-O3 -arch i386 -arch x86_64' CXXFLAGS='-O3 -fno-common -arch i386 -arch x86_64' ./configure --with-php-config=/Developer/SDKs/MacOSX10.6.sdk/usr/bin/php-config; make -j6;sudo make install
  sudo echo "extension=mcrypt.so" >> /etc/php.ini

  # Check if the new extension is avaible
  php --info | grep mcrypt

  # restart apache
  sudo apachectl restart
