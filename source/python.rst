===================
Python Notes
===================

Abelson & Sussman from Structure and Interpretation of Computer Programs
   | Programs must be written for people to read, 
   | and only incidentally for machines to execute.

Strings
-------

length of the string

.. code-block:: python

   len(strName)

second char of string

.. code-block:: python

   strName[1]

return chars at index 1 to index 2 (up to but not including the upperbound)

.. code-block:: python

   strName[1:3]

return strName string 8 times

.. code-block:: python

   strName * 8

strings are still immutable in python!

.. code-block:: python

   strName[0] = 'a' # THIS CAUSES AN ERROR

find first 'ab' in the string else -1

.. code-block:: python

   strName.find('ab')

return string that replaced all ab's with cd's

.. code-block:: python

   strName.replace('ab', 'cd')

split string into a list (comma delimiter)

.. code-block:: python

   strName.split(',')

splits string at spaces

.. code-block:: python

   str.split()[-1]

return uppercase of string

.. code-block:: python

   strName.upper()

return true if all chars are letters

.. code-block:: python

   strName.isalpha()

return true if all chars are integers (no floating points)

.. code-block:: python

   strName.isdigit()

removes whitespace characters on the right side

.. code-block:: python

   strName.rstrip()

implicit concatentation, returns hello

.. code-block:: python

   strName = 'he' 'llo'

does not give you file path due to \n and \t

.. code-block:: python

   wrong_formatting = 'C:\new\test'
   right_formatting = r'C:\new\test' #the r(aw) runs off escapes

convert number into a string

.. code-block:: python

   str(num)

add string quotes and backslashes

.. code-block:: python

   repr(str)

adding values into strings

.. code-block:: python

   'my {0} string'.format('x')
   'my {name}'.format(name='john')

Lists
-----

adds string 'yo' at the end of list

.. code-block:: python

   mList.append('yo')

remove the element at index 3

.. code-block:: python

   mList.pop(3)

removes first 'a' element in the list

.. code-block:: python

   mList.remove('a')

sorts list

.. code-block:: python

   mList.sort()

reverses order of elements

.. code-block:: python

   mList.reverse()

return the number of times a value occurs in a list

.. code-block:: python

   mList.count()

'*' is a repeater::
   
   [1,2] * 3 becomes [1,2]+[1,2]+[1,2]

appending and extending a list

.. code-block:: pycon

    >>> mList = ['a', 'b']
    >>> mList.append(['c', 'd'])
    >>> mList
    ['a', 'b', ['c', 'd']]
    >>> mList.pop()
    ['c', 'd']
    >>> mList
    ['a', 'b']
    >>> mList.extend(['c', 'd'])
    >>> mList
    ['a', 'b', 'c', 'd']

Librarys
--------

keys must be immutable objects (like strings)

.. code-block:: pycon

    >>> lib = {
    ...     'book': 
    ...        {'title':'potter', 'pages':15, 'chapters':2},
    ...     'location':
    ...        {'street':'Dean', 'num':12}
    ... }
    >>> lib['book']['title']
    'potter'
    >>> lib.has_key('hello')
    False

Files/IO
--------

val = raw_input()
   like C++'s cin << value

value = raw_input("Prompt:")
   like cout >> "Prompt:"; cin << value

open('data.txt', 'w')
   makes a new file/erases old file with same name

open('data.txt', 'r')
   files can only be read

open('data.txt', 'a')
   open file for appending (appended data goes to the end)

f.write('Hello\n')
   writes string to file

f.close()
   writes output buffers to disk, closes

open('data.txt')
   'r' is the default processing mode

f.read()
   output is 'Hello\n'

f.readlines()
   returns list of all the lines

for line in f:
   loops over file object, more memory efficient

try-finally type syntax to ensure file is closed properly

.. code-block:: python

   with open('data.txt', 'r') as f:
      data = f.read()
   f.close()

   with open('data.txt') as f:
      for line in f:
         print line

pickle.dump(x, f)
   this will write python object 'x' to file 'f' references

x = pickle.load(f)
   this will make an 'x' object from what was written to the 'f' file
   reference

.. warning::

   objects that can be stored are known as persistent objects (serializable),
   its is not very secure to open load a file using pickle.load([file])

Flow Control
------------

Basic loops

.. code-block:: pycon

    >>> L = [1,2,3,4,5]
    >>> squares = [x ** 2 for x in L]
    >>> squares
    [1, 4, 9, 16, 25]
    >>> squares = []
    >>> for x in L:
    ...     squares.append(x**2)
    ... 
    >>> squares
    [1, 4, 9, 16, 25]
   
continue
   jumps to the beginning of the loop

Error handeling

.. code-block:: python

   try:
      num = int(foo)
   except:
      print 'Something went wrong!'
   else:
      print '{0} - it worked!'.format(foo)

Exceptions
----------

class ShortInputException(Exception):
raise ShortInputException()

Type Checking
-------------

.. code-block:: pycon

    >>> L = [1,2,3]
    >>> type(L)
    <type 'list'>
    >>> if type(L) == type([]):
    ...     print 'Testing the type'
    ... 
    Testing the type
    >>> if type(L) == list:
    ...     print 'Testing the name'
    ... 
    Testing the name
    >>> if isinstance(L, list):
    ...     print 'L is an instance of list!'
    ... 
    L is an instance of list!

ORDER OPERATION
---------------

::

    precedence  #left to right
    assignment  #right to left a=b=c -> a=(b=c)


SCOPE
-----

global x
   makes x global
nonlocal
   can get variable from outher class (assuming in subclass)

   
FUNCTIONS
=========

.. code-block:: pycon

    >>> def func(a, b=5):
    ...     print (a, b)
    ... 
    >>> func(5)
    (5, 5)
    >>> func(2, b=8)
    (2, 8)
    
Functions with keyword arguments

.. code-block:: pycon

    >>> def totals(init=5, *nums, **keys):
    ...     count = init
    ...     for num in nums:
    ...             count += num
    ...     for key in keys:
    ...             count += keys[key]
    ...     return count
    ... 
    >>> print(totals(10, 1, 2, 3, girls=10, guys=80))
    106


In python a methods first formal parameter dictates the type of method it will
be::

    def meth(self, x):  #instance method
    def meth(x):        #static method
    def meth(cls, x):   #gets class not instance


MODULES
=======

    import sys
        sys.argv    #list of strings
                    #sys.argv[0] = file.py not the first cmd arg
        sys.path    #list of dir names where modules are imported from
        sys.modules #table of modules that have been initialized, indexed
                    #by module name
    
    #structure
    package/
    __init__.py
    module1.py
    subpackage/
        __init__.py
        module2.py
        
    If you import the module, then __name__ is the module's filename, 
    without a directory path or file extension.
    
    When you run the module directly __name__ is __main__ 
    
    dir(object)     #returns all attributes of a given object
    help(object)    #returns a lot of information about that object, and all its classes
    
    a module's attributes share the same namespace as global names defined in the module
    module attributes are writable, can be deleted with "del" statement
        del modname.attribule   #removes attribute from modname object

        
CLASS
    __init__(self, ...)    #run as soon as object is instantiated
    __del__(self)          #called just before object is destoryed
    __str__(self)          #called when using print or str() functions
    __lt__(self, other)    #called when < used
    __getitem__(self, key) #called when x[key] indexing is used
    __len__(self)          #?
    
    __doc__                #the docstring
    
    namespace is created upon class definition
    
    isinstance()
    issubclass()

TRICKS
    x = None    # None placeholder

    obj1 = obj2
    obj1 == obj2    #do they have the same value?
    obj1 is obj2    #points to same object
                    #small integers and strings will also point to the same place
                    #if their values are the same due to caching

    dir(object)             #returns all methods of object
    callable(object)        #returns True if object can be called
    getattr(object ,method) #returns a function object if object is a module and 
                                method is the name of a function in that module
    
    import sys
    sys.getrefcount(1)	#returns the number of pointers to a shared piece of memory

    if len(my_object) > 0:
    if my_object:           #same as above because 0 is considered
                            #false while everything else is true

    string = 'Hi there'
    if string.find('Hi') != -1:
    ##or##
    if 'Hi' in string:
    
    numbers = [1, 2, 3]
    squares = []
    for number in numbers:
        squares.append(number*number)
    ##the faster way##
    numbers = [1, 2, 3]
    squares = [number*number for number in numbers]
    
    numbers = [1, 2, 3]
    squares = map(lambda x: x*x, filter(lambda x: x<4, numbers))
    ##or##
    numbers = [1, 2, 3]
    squares = [number*number for number in numbers if number < 4]
    
    #using zip
    letters = ['a', 'b', 'c']
    numbers = [1, 2, 3]
    squares = [1, 4, 9]
    ziplist = zip(letters, numbers, squares)
        #[('a', 1, ,), ('b', 2, 4), ('c', 3, 9)]
                            
    print '{0:10}'.format('name')	#:10 = min number of chars wide	(format tip)

       
PYDOC
    pydoc [module]      #produces plaintext on console
    pydoc -w [module]   #creates html output in current dir
    pydoc-p 5000        #html output @ localhost:5000/[module]
    
PYTHON lIBRARY
    chr(str)        #Character - takes str, returns ASCII num
    ord(int)        #Ordinal - takes int, returns ASCII letter


PEP8
====

 - Limit all lines to a maximum of 79 characters. Limiting the length to 72 characters is recommended.
 - prefered place to break around a binary operator is after the operator, not
   before it
 - Seperate top-level functions and class definitions with two blank lines.
 - imports should usually be on a seperate line::

      #Good
      import os
      import sys

      #Bad
      import os, sys

      #This is ok
      from subprocess import Popen, PIPE

 - imports should be in this order::

      standard library imports
      related third party imports
      local application/library specific imports

 - you should put a blank line between each group of imports.
 - don't use spaces around the '=' sign when used to indicate a keyword
   argument or a default parameter value.::

      #Good
      def complex(real, imgg=0.0):
         return magic(r=real, i=immg)

      #Bad
      def complex(real, imgg = 0.0):
         return magic(r = real, i = imgg)

 - you should use two spaces after a sentence-ending period.
 - don't use O (uppercase o), I (uppercase i), and l (lowercase L)
 - use ''.startswith() and ''.endswith() instead of string slicing to check
   for prefixes or suffixes.::

      #Good
      if foo.statswith('bar'):

      #Bad
      if foo[:3] == 'bar':

 - when checking if an object is a string, keep in mind that it might be a
   unicode string too! In Python 2.3 str and unicode have a common base class,
   basestring, so you can do::

      if isinstance(obj, basestring):

Doc String
----------

How the docstring should be formated::

   """Return a foobang

   Optional plotz says to frobnicate the bizbaz first.

   """

Types of methods
----------------

Interface
   methods are presented without a prefix

Internal
   methods which may be over-ridden are prefixed by a single underscore

Private
   methods are prefixed by a double underscore

PEP8 Example
------------

.. code-block:: python

    class Rectangle(Blob):

        def __init__(self, width, height,
                     color='black', emphasis=None, highlight=0):
            if width == 0 and height == 0 and \
               color == 'red' and emphasis == 'strong' or \
               highlight > 100:
                raise ValueError("sorry, you lose")
            if width == 0 and height == 0 and (color == 'red' or
                                               emphasis is None):
                raise ValueError("I don't think so -- values are %s, %s" %
                                 (width, height))
            Blob.__init__(self, width, height,
                          color, emphasis, highlight)

Naming Conventions
------------------

::

    Functions, Methods, and Attributes => joined_lower
    Constants => ALL_CAPS, joined_lower
    Classes => StudlyCaps


The Meta class
==============

http://stackoverflow.com/a/6581949/465270

classes are also objects therefore you can
- assign it to a variable
- copy it
- add attributes to it
- pass it as a function parameter

- metaclass is the stuff that creates class objects
- python will use the metaclass to create the class
- if python does not find a meta class then the metaclass type will be used to
  create the class

The breakdown
-------------

.. code-block:: python

    class Foo(Bar):
        pass

Is there a __metaclass__ attribute in Foo?

If yes, create in memory a class object, with the name Foo by using what is in
__metaclass__.

If Python can't find __metaclass__, it will look for a __metaclass__ in
Bar (the parent class), and try to do the same.

If Python can't find __metaclass__ in any parent, it will look for a
__metaclass__ at the MODULE level, and try to do the same.

Then if it can't find any __metaclass__ at all, it will use type to create
the class object.
