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

Running:

.. api-inline :: dojo.byId
    :examples:  

CodeGlass
---------

A special popup to control various JavaScript example is also included (maybe we should rewrite CodeGlass?).


.. _dojo: http://dojotoolkit.org
