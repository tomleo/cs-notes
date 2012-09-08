Constants
---------------

constants can't be changed

.. code-block:: ruby

   EmpireStateBuilding = "350 5th Avenue, NYC, NY"
   
Objects
-----------

Everthing is an object. Objects created via a constructor. Standard constructor is "new"

.. code-block:: ruby

   item_one = LineItem.new
   
Methods
-----------

! and ? can be used in method names

method definition starts with def

.. code-block:: ruby

   def yourage ( dob )
      #code goes here
   end

Class Methods
-------------

use double colon (creates instance object)

.. code-block:: ruby

   Door::new( :oak )
   
you can print the an objects type/class

.. code-block:: ruby

   print 5.class                       # prints 'Integer'
   print 'wishing for antlers'.class   # prints 'String'
   print WishMaker.new.class           # prints 'WishMaker'

accessor methods are created for you.

.. code-block:: ruby

   attr_accessor  :robot1  #creates get/set methods for robot1
   attr_reader    :robot2  #creates get method for robot1
   attr_writer    :robot3  #creates set method only
   
privacy is done like this

.. code-block:: ruby

   class Myclass
      def m1   #public method
      end
      
      protected
      
      def m2   #this method is protected
      end
      
      private
      
      def m3   #this method is private
      end
   end
   
Modules
----------

Hold collection of methods.
Act as a namespace.
Allow to share funcionality between classes. (

Variables
----------

variables that begin with $ are global

.. code-block:: ruby

   $Chucky_bacon
   
variables begin with @ are instance variables

.. code-block:: ruby

   @my_chunky_bacon
   
class variables begin with @@

.. code-block:: ruby

   @@super_chunky_bacon
   
code blocks can be created with {/} or do/end

.. code-block:: ruby

   2.times { print "Hellow World" }
   
   loop do
      print "Another Hello"
      print "World"
   end

you can pass arguments to blocks using the | character

.. code-block:: ruby

   { |x,y| x + y }

Range
-----

creates range of numbers or chars

.. code-block:: ruby

   (1..3) # numbers 1-3
   
   ('a'..'z') # letters a-z
   
   (0...5) # numbers 0-4

Arrays
-------

.. code-block:: ruby

   [1, 2, 3]
   
   ['a', 'b', 'c']
   
Shortcut for creating arrays

.. code-block:: ruby

   a = %w{ a b c }
   
Hashes
-----------

aka dictionary

.. code-block:: ruby

   {'a' => 'apple', 'b' => 'bannana'}
   
String
--------

Single quoted strings simply contain text, Double quoted strings allow for expression interpolation

.. code-block:: ruby

   print '2+2=#{2+2}' #returns>  2+2=#{2+2}

   print "2+2=#{2+2}" #returns>  2+2=4
   
Double quoted strings that span multiple lines can we written using

.. code-block:: ruby

   %{This sentence
      Spans
      Lots
      Of Lines}


   
Operators
----------

<<
   concatenation operator, appends
   
   .. code-block:: ruby
   
      email = "tom"
      email << "@tomleo.com"
      
      
nil?
   checks if method is nill. nill is an object.
   
   .. code-block:: ruby
   
      print( if myfunction.nil?
         "The Function is nill"
      else
         "The Function has value!"
      end )

==
   This is a method
   
   .. code-block:: ruby
   
      if baconTastesGood.==(true)
         #Yum
         
      if baconTastesGood==(true)
         #Yum
         
      if baconTastesGodd
         #Yum
         
||
   Or operator
   
a operation b

.. code-block:: ruby

    count += 1
    price *= discount
    count ||= 0    #count = count || 0

gsub
   short for global subsitution
   
File class
------------

.. code-block:: ruby

   File::read("notefile.txt")
   File::rename("oldfile.txt", "newfile.txt")
   File::delete("newfile.txt")
   File::open('notes.txt', 'w')  #writes to new file
   File::open('notes.txt', 'r')  #reads from file
   File::open('notes.txt', 'a')  #adds to end of file
   
Flow of control
----------------

.. code-block:: ruby

   case grade
   when 100
      "A+"
   when 90..99
      "A"
   when 80..89
      "B"
   when 70..79
      "C"
   when 60..69
      "D"
   when 0..59
      "F"
   end
   
Regular Expressions (regex)
---------------------------

=~ is the match operator to test strings against regular expressions

.. code-block:: ruby

   if line =~ /P(erl|ython)/
      puts "What other scripting lanuage is work learning?"
   end




   


