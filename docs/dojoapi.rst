.. _docs/dojoapi:

Dojo Specific API Extensions
============================

A special ``rst`` processor is included with this wiki to handle some dojo_ documentation needs.

.. contents ::

API Links
---------

Include a link to the official API page for some passed function.

.. code :: bash

    .. api-link :: dojo.query

Will produce:

.. api-link :: dojo.query

This is done to eliminate the need to hardcode versions into links, or to manage the links yourself.

API Inline
----------

It is possible to inline the available API information from another page. 

.. code :: bash

   .. api-inline :: dojo.byId

Will produce:

.. api-inline :: dojo.byId

Reduced API Samples
-------------------

There is a way to only show parts of some API information. If there are no additional arguments, everything is shown. Pass any additional arguments, and only those items are shown. They are based on their ``jsdoc`` keywords, like **example:**

For example, this will only show the ``examples`` section of the API doc:

.. code-block :: javascript

  .. api-inline :: dojo.byId
     :examples:

Output is:

.. api-inline :: dojo.byId
    :examples:  

Adding ``:no-titles:`` makes it only output the raw for whatever part. 

.. api-inline :: dojo.byId
    :no-titles:
    :examples:
    :signature:

Just a signature:

.. api-inline :: dojo.byId
    :signature:
    :no-titles:

Just Some long signature information, with a ``Parameters`` heading:

.. api-inline :: dojo.byId
    :longsignature:

Caching is in place. The first hit to the API info is a network request. That is saved, so multiple ``api-inline`` directives within the same page (and within a running instance before restart) will all use the same cache.

CodeGlass
---------

A special popup to control various JavaScript example is also included (maybe we should rewrite CodeGlass?).


.. _dojo: http://dojotoolkit.org
