.. _docs/CodeGlass:

Using CodeGlass
===============

.. contents ::

Actually want to rewrite codeglass. This is a test page from rst to ensure lots of options are available.

Basic Usage
-----------

The most basic of examples:

.. code-example ::
  
  This is the first bit of inner content of the code example. It is ``light`` markdown. 

  .. cv :: javascript
    :label: The JavaScript. Ideally this would be infered from the preceding paragaph. 
    <script>
        dojo.ready(function(){ 
            console.warn(dojo.query("#bar"))
        });
    </script>

  This test is after the js and before some raw html:

  .. html ::
     
    <div id="bar"><p>Hi!</p></div>


Errors
------

This throws an exception before onload:

.. code-example ::

  .. js ::

     <script>var x = y</script>



That's all, folks.
