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

  .. js ::
 
    <script>
        dojo.ready(function(){ 
            console.warn(dojo.query("#bar"))
        });
    </script>

  .. html ::
     
    <div id="bar"><p>Hi!</p></div>

This throws an exception before onload:

.. code-example ::

  .. js ::

     <script>var x = y</script>



That's all, folks.
