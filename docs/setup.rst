.. _docs/setup:

Advanced Setup
==============

.. contents ::

Trouble Getting Started
-----------------------

If running ``./wiki.py`` doesn't work out of the box, you are probably missing some dependencies. To get this running in 
various random environments (osx, centos|suse/linux so far) we've been relying on ``virtualenv``

You'll need python > 2.5 to use this, at the least. Setup a ``virutalenv`` for the default install:

.. code :: bash

    $ virtualenv tmp
    $ source tmp/bin/activate
    
Then run setuptools (aka ``easy_install``):

.. code :: bash

    (virtualenv)$ easy_install Pygments
    (virtualenv)$ easy_install docutils
    (virtualenv)$ easy_install ldap-python

And so on for various packages it complains about. There aren't many.

Proxy via Apache
----------------

The static files should be processed by Apache or similar. Using Apache/ProxyPass is easy. Run the wiki 
server on a specified local port, and proxy the requests to the application, intercepting requests to ``_static``

.. code :: xml

    <VirtualHost *:80>

        ServerName local.servername
        ProxyPass /_static !
        Alias /_static {pathTo}/rstwiki/_static
        ProxyPass / http://localhost:4200/
        ProxyPassReverse / http://localhost:4200/
        ProxyPreserveHost On
        
        <Directory {pathTo}/rstwiki/_static>
            Order allow,deny
            Allow from all
        </Directory>
    
    </VirtualHost>

Restart Apache and hit http://local.servername ... If the server is public, you may also want to include an 
Alias directive pointing to a robots.txt

If it doesn't start right up, you'll likely need to install some dependencies.

LDAP Information
----------------

LDAP integration is crude, and specific to the Dojo Foundations's CLA system. You can't use it. 

Full support would be awesome. Patches/ideas welcome.

Always set this to False, unless you ``want`` or ``need`` to use Dojo's LDAP (you being me, and a few others). In which case, 
enabling this will prevent changes via the wiki without first authorizing themselves via Dojo's LDAP service.

VCS Integration
---------------

Version control transparency is key. The **entire** point of this wiki is to enable folks to transparently edit a tree of ``.rst`` files
while **easily** maintaining said tree in whatever formal VCS they use.

rsiWiki provides ``git`` and ``svn`` integration, with an ambigious ``local`` setup to allow the wiki to be used as a local 
server, processing local changes on the fly. 

git
~~~

TODOC: details about git integration

svn
~~~

TODOC: details about subversion integration

local
~~~~~

TODOC: how to use this for fun, against a non-vcs tree, or how to use this against a VCS tree but disable VCS integration 
(to allow manual commit/push/management naturally, but allow realtime rendering)
