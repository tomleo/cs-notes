=========
XML Notes
=========

No prebdefined tags, define your own, XML schema or DTD to descrive data
    
XML used to create XHTML and RSS::

    <?xml version="1.0" encoding="ISO-8859-1" ?>


XML declaration defines version and encoding
        
XML must contain root element (parent of other elements)

Syntax Rules
============

- closed tags
- case sensitive tags
- elements properly nested
- must have root element
- attributes quoted
- errors stop XML app

XML comment::

   <!-- comment -->


CDATA
   like comments, everything inside ignored by parser::

      <![CDATA[   comment goes here      ]]>


- white spaces are not removed
- attributes have info not part of data
- attributes must be enclosed into qutoes single or double
- meta data should be stored as attributes
    
Sample Code::

    <?xml version = "" encoding = "" ?>
    <root element>
        <child>blah</child>
        <elements>blach</elements>
    </root element>
    <!-- comment -->


Embeded XML (in html)::

   <xml id="note" src="note.xml"></xml>
    

XML table::

    <table><tr>
        <td>Apples</td>
    </tr></table>


XML table with more info::

    <h:table>
        <h:name>Tom</h:name>        <!--Prefix tags to avoid element name conflicts-->
        <h:width>80</h:width>
        <h:length>80</h:length>
    </h:table>
 

Namespace of element associates to child elements with same prefix::

   xmlns:namespace-prefix = "namespace URL"


- saving xml as unicode to understand foreign chars
  creates errors in netscape if xml has foreign chars
  netscape error if encoding is UTF-16

Escape Chars::

    &lt;    = <
    &gt;    = >
    &amp;   = &
    &apos;  = '
    &quot   = "


XML DTD
    Defines structure of XML documet, with list of legal elements
    alternative to schema
    
XML STYLE
    CSS to style XML::

      <?xml-stylesheet type="text/css" href="cd_catalog.css" ?>
   

    XSL (extensible stylesheet language)
    
Parse XML via Javascript::

    var xmlDoc = new ActiveXObject("Microsoft.XMLDOM");     //create instace of IE parse
    var xmlDoc = document.implementation.createDocument("ns", "root", null);    //ns = name space used, root = xml root element
    xmlDoc.async="false";   //does not execute until full script is loaded


