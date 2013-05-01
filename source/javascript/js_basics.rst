================
JavaScript Basics
=================

Vars
-----

vars are case sensitive, and must start with letter

.. code-block:: javascript

   var x=5;
   var name="value"

Looping n Shit
==============

.. code-block:: javascript

   for (var = startval; var <= endval; var = var + increment){ }

   for(i=0, j=0, k=0; i<50; i++, j++, k++){ }
    
   for (var in array){ }

   while (var <= endval) { }

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

Syntax n Shit
=============

::

   Comments
   ---------------------------------
   //
   /*  */


   Arithmetic  +, -, *, /, %, ++, --
   Assignment  =, +=, -=, *=, /=, %=
   Comparison
      ==       equal to
      ===      equal to (value + type)
      !=       not equal to
      >        greater than
      <        less than
      <=       less than or equal
      >=       greater than or equal
      &&       and
      ||       or

   Escapes
   ---------------------------------

   \'       single quote
   \"       double quote
   \&       ampersand
   \\       backslash
   \n       newline
   \r       carriage return
   \t       tab
   \b       backspace
   \f       form feed

   Bool Objects
   ---------------------------------
   False
      0, -0, null, "", false, undefined, Non

   True
      everything else


Objects
========

are essentialy key-value pairs

.. code-block:: javascript

    var obj = {
      "name": "myObj",
      "date": "10/4/03"
    };

    //You don't need to quote variables the following will be the same

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



Arrays
======

.. code-block:: javascript

   var myArr = new Array();

arrays are objects
arrays have a length property
array has a push operator

.. code-block:: javascript

  var stack = ["a", "b"];
  stack.push("c"); // returns 3 (the new length?) and stack now equals ["a", "b", "c"]

  stack["push"]("d"); //returns 4 and stack now equals ["a", "b", "c", "d"]

  stack[10] = "j"; //will add j to 10th number

you can add properties to array objects

.. code-block:: javascript

    var A = ["a", "b"];
    A.newProperty = "hello";

for-in loop will print all indexes as well as properties

.. code-block:: javascript

    var date = {
      day: 4,
      month: 2
    };

    for(var i in date) {
      console.log(i);         //returns day, month
      console.log(date[i]);   //returns 4, 2
      console.log(date.i);    //ERROR: this will not work
    }

Functions
=========

function

.. code-block:: javascript

   function functionname(var, var2) {
      //code goes here
   }

function literal definition

.. code-block:: javascript

   var square = function(var, var2) {
      //code goes here
   }

functions are objects you can add properties to functions

.. code-block:: javascript

   //property added to foo function object
   foo.grilledChicken = "YUM!"; 


SYNTAX
======

::

    //                  Oneline comment
    /**/                Multi-line comment

    var x=5;            vars are case sensitive,
    var name="value"    and must start with letter

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


Functional Programming
======================

Array Comprehension
-------------------
[i * i for i of [1, 2, 3]];

Map
---
[1, 2, 3].map(function (i) { return i * i });
[650,123,4567].map(String).join('-');

Filter
------
[1,4,2,3,-8].filter(function(i) { return i < 3 });

this
----

this in the global context refers to the window object, *this* is also global
inside functions if *use strict* is not being used.

.. code-block:: javascript

   console.log(this === window); // true

   //if not using strict
   function checkThisOut () {
      console.log(this === window); // true
   }

   //if using stricut 
   function checkThisOut () {
      console.log(this === window); // false
   }
