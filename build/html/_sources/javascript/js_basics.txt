================
JavaScript Basics
=================

Comments
--------   

Single-line comment::
    
    //

Multi-line comment::

    /* 
    */

Vars
-----

vars are case sensitive, and must start with letter

.. code-block:: javascript

   var x=5;
   var name="value"


Operators
---------

==========  ======================
Type        Symbol
----------  ----------------------
Arithmetic  +, -, *, /, %, ++, --
Assignment  =, +=, -=, *=, /=, %=
==========  ======================

Comparison
----------

======   ========================
Symbol   Meaning
------   ------------------------
==       equal to
===      equal to (value + type)
!=       not equal to
>        greater than
<        less than
<=       less than or equal
>=       greater than or equal
&&       and
||       or
======   ========================

Function
---------

.. code-block:: javascript

   function functionname(var, var2) {
      //code goes here
   }

function literal definition

.. code-block:: javascript

   var square = function(var, var2) {
      //code goes here
   }

loops
---------

.. code-block:: javascript

   for (var = startval; var <= endval; var = var + increment){
      //code
   }

   for(i=0, j=0, k=0; i<50; i++, j++, k++){
		document.write("i=" + i + " ");
		document.write("j=" + j + " ");
		document.write("k=" + k);
		document.write("<br />")
	}

   //This will yeild
   /*
   i=0 j=0 k=0 
   i=1 j=1 k=1 
   i=2 j=2 k=2 
   i=3 j=3 k=3 
   i=4 j=4 k=4 
   i=5 j=5 k=5 
   i=6 j=6 k=6 
   i=7 j=7 k=7 
   i=8 j=8 k=8 
   i=9 j=9 k=9 
   */
    

   for (var in array){
      //code
   }

   while (var <= endval) {
      //code
   }

   do {
      //code
   }while(var <= endval);

   try {
      //somethin 
   } catch(err) {
       //do something
   }

break;
   breaks from loop
continue;
   breaks from current loop, move to next val

Excapes
--------

======   ================
Symbol   Value
======   ================
\'       single quote
\"       double quote
\&       ampersand
\\       backslash
\n       newline
\r       carriage return
\t       tab
\b       backspace
\f       form feed
======   ================

Arrays
---------

.. code-block:: javascript

   var myArr = new Array();

Bool Objects
------------

False
   0, -0, null, "", false, undefined, Non

True
   everything else

Numbers
----------

Math
   Math.round(double)
   Math.random()
   Math.max(9,5)
   Math.min(#, #)

Special Numbers
   Infinity
   Nan
      Not a number (Does not exist)
      Can't be compared to other numbers or itself (isNan used to test if num is Nan)


Objects
========

are essentiall key-value pairs

.. code-block:: javascript

    var obj = {
      "name": "myObj",
      "date": "10/4/03"
    };

You don't need to quote variables the following will be the same

.. code-block:: javascript

    var obj = {
      name: "myObj"
      date: "10/4/03"
    };

Objects members can be called like a dictionary or an object::

    obj.name
    obj["name"]

Objects are mutable, key-value pairs can be added

.. code-block:: javascript

    var obj = {
      name: "foo"
    };

    obj.age = 5

You can create objects within objects in javascript

.. code-block:: javascript

    var obj = {
      name: "foo",
      date: {
        day: 1,
        month: 3,
        year: 2012
      }
    };

Function Operator
-----------------

.. code-block:: javascript

    var func = function() {
      console.log("hello");
    };

    func(); // "hello"

    var func = function( parm ) {
      console.log(parm);
    };

    func("hello"); // "hello"


Scope
------

you can get values of an outer object from an inner object

.. code-block:: javascript

    var obj = {
      date: {
        day: 1,
        month: 1,
        year: 2012,
        formatDate: function() {
          return this.month + "/" + this.day + "/" + this.year;
        }
      }
    };

when you invoke a function as a method i.e. obj.date.formatDate() then you get
access to properties of obj::

   obj.date.formatDate(); // "1/1/2012"


Interate over objects with "for in loop"
----------------------------------------

.. code-block:: javascript

    var date = {
      day: 4,
      month: 2
    };

    for( var i in date ) {
      console.log(i);
    }

    /*
    day
    month
    */

    for( var i in date ) {
      console.log(date[i]);
    }

    /*
    4
    2
    */

    for ( var i in date ) {
      console.log(date.i);
    }

    // This will not work!


Arrays
======

arrays are objects
arrays have a length property
array has a push operator

.. code-block:: javascript

  var stack = ["a", "b"];
  stack.push("c"); // returns 3 (the index?) and stack now equals ["a", "b", "c"]

  stack["push"]("d"); //returns 4 and stack now equals ["a", "b", "c", "d"]

  stack[10] = "j"; //will add j to 10th number

you can add properties to array objects
NOTE: a for-in loop will print all indexes as well as properties

.. code-block:: javascript

    var A = ["a", "b"];
    A.newProperty = "hello";

Functions
=========

decalring a named function

.. code-block:: javascript

    function foo ( chickenParm ) {
      console.log( chickenParm )
    }

    //invoke function
    foo("SKIOOOOOO");

    /*SKIOOOOO*/

functions are objects you can add properties to functions

.. code-block:: javascript

    foo.grilledChicken = "YUM!"; //property added to foo function object
    console.log( myAlert.newProp );
    /*YUM!*/

MARKUP
======

  <script type="text/javascript"></script>
  <script src="external.js"></script>

SYNTAX
======

::

    //                  Oneline comment
    /**/                Multi-line comment

    var x=5;            vars are case sensitive,
    var name="value"    and must start with letter


Operators
=========

::

    Arithmetic          +, -, *, /, %, ++, --
    Assignment          =, +=, -=, *=, /=, %=
    Comparison          ==      equal to
                        ===     equal to (value + type)
                        !=      not equal to
                        >       greater than
                        <       less than
                        <=      less than or equal
                        >=      greater than or equal
                        &&      and
                        ||      or

Function
========

.. code-block:: javascript

    function functionname(var, var2,...){ /*code*/ }

    //function literal definition
    var square = function(var, var2,...){ /*code*/ }

Looping
=======

.. code-block:: javascript

    for (var = startval; var <= endval; var = var + increment){ /*code*/ }
    for (var in array){ /*code*/ }
    while (var <= endval) { /*code*/ }
    do { /*code*/ }while(var <= endval);
    try { /*somethin*/ }catch(err) { /*do something*/  }

    break;      break from loop
    continue;   break from current loop, move to next val

Escapes
=======

::

    \'      single quote
    \"      double quote
    \&      ampersand
    \\      backslash
    \n      newline
    \r      carriage return
    \t      tab
    \b      backspace
    \f      form feed

Define Array
============

.. code-block:: javascript

    var myArr = new Array();


Bool Objects
============

::

    FALSE   0, -0, null, "", false, undefined, Non
    TRUE    everything else...

Numbers
=======

::

    Math.round(double)
    Math.random()
    Math.max(9, 5)
    Math.min(#, #)

Special Nums
------------

Infinity
Nan
   Not a number (Does not exsist) Can't be compared to other nums or itself (isNan - used to test if num is Nan)

Hex & Octal Literals
--------------------

hex literal begins with "0x or 0X"::

   0xff    //255
   0xCAFE911

some implementations of JS allow octal literals. 
octal literals begin with 0 and followed by #'s 0-7::

    0377   //255

avoid writing literals with a leading zero! you cannot known wheather an implementation
will interpret it as an octal or decimal value

IO
=====

document.write()
   Like system.out.print(), cout, ect.

Strings
=======

::

    \u  unicode
    concat with +
    ""'hey'"" / '""hey""'   -->     'hey' / "hey"

    s.length
    s.charAt(s.length-1)
    s.substring(1,4)
    s.indexOf('a')

double quotes can be in single quoted area and vice versa::

    "Text 'yo' more text"

Tricks and Methods
==================

A way to dynamicaly access a variable
Look threw DOM for all elements with specified tag name

.. code-block:: javascript

    var myVariable = document.getElementById(myElement); 
          
    myVariable.style.display = "block";  
    myVariable.style.backgroundColor = "#f00";  
    myVariable.style.border = "solid 1px #00f";

Create an array

.. code-block:: javascript

    var myLinkCollection = document.getElementsByTagName("a"); 

    for (i = 0; i < myLinkCollection.length; i++) {  
        if (myLinkCollection[i].className == "link_class") {  
            myLinkCollection[i].onclick = function() {  
                myLinkCollection[i].style.backgroundColor = "#f00";  
            }  
        }  
    }

Create a new element

.. code-block:: javascript

    var myNewListItem = document.createElement("li");  
    var myNewLink = document.createElement("a");

Remove Child element

.. code-block:: javascript

    var myLinkList = document.getElementById("list");  
    var myRemovedLink = myLinkList.lastChild;  
    myLinkList.removeChild(myRemovedLink);  

Get Attribute

.. code-block:: javascript

    var myLinkFive = document.getElementById("link_5");  
    var myLinkAttribute = myLinkFive.getAttribute("rel");  

Random Style Sheet

.. code-block:: javascript

    function rand(){
        return Math.round(Math.random()*(css.length-1));
    }

    var css = new Array(
        '<link rel="stylesheet" type="text/css" href="default.css">',
        '<link rel="stylesheet" type="text/css" href="style2.css">',
        '<link rel="stylesheet" type="text/css" href="style3.css">',
        '<link rel="stylesheet" type="text/css" href="style4.css">',
    );

.. code-block:: html

    rand = rand();
    document.write(css[rand]);

3RD Party
=========

Fixing PNG's in IE6 with DD_BelatedPNG
http://www.dillerdesign.com/experiment/DD_belatedPNG/

.. code-block:: html

    <!--[if IE 6]>
        <script src="DD_belatedPNG.js"></script>
    <![endif]-->
    <script type="text/javascript">
        DD_belatedPNG.fix(".linkButton");
    </script>

Super Class Inheritance with JavaScript
=======================================

 - Object Oriented
 - Should not rely on the DOM

Prototypal Inheritance
----------------------

 - No classes - just Objects
 - Objects inherit from Objects
 - Objects contain a "link" to another object. The "parent" object is just a
   regular object


Events and Responses
====================

.. code-block:: javascript

   var a = document.querySelector('a'); // grab the first link in the document
   a.addEventListener('click', ajaxloader, false);
   //ajaxloader() function is the even listener



