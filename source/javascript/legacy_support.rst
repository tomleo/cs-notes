IE6
===

Fixing PNG's in IE6 with DD_BelatedPNG
--------------------------------------

http://www.dillerdesign.com/experiment/DD_belatedPNG/

.. code-block:: html

    <!--[if IE 6]>
        <script src="DD_belatedPNG.js"></script>
    <![endif]-->
    <script type="text/javascript">
        DD_belatedPNG.fix(".linkButton");
    </script>
