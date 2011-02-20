.. _docs/test:

Test
=====

This is a test. Thanks.

Sample code:

.. code :: javascript

    dojo.ready(function(){
        dojo.byId("bar").innerHTML = "foo!";
    });

Testing a block with line numbers:

.. code :: javascript
    :linenos:
    
    // with line numbers?
    console.warn("foo");
    
CV version:

.. cv :: javascript

    dojo.ready(function(){
        dojo.byId("bar").innerHTML = "foo!";
    });

In A compound:

.. code-example::

    Some Text within the compound before js directive
    
    .. cv :: javascript
    
        dojo.ready(function(){
            dojo.byId("bar").innerHTML = "<p>after!</p>";
        });
        
    Text in the compound after JS (example throws if id='bar' unfound ...

    .. html ::

        <div id="bar"><p>before</p></div>

Text after the compound block.

.. code-example ::

    Example with all types

    .. cv :: javascript

       console.warn("hi");

    Text before CSS. HTML has no pretext to show spacing on in-block directives.

    .. cv :: css 

       body, html { color:red }
       .foo { color:green }

    .. cv :: html

       <div class="foo">Hi</div> There
    
That's All, Folks.
