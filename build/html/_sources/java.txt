==========
Java Notes
==========

OOP Basics
==========

Static Method
-------------

a method that preforms an operation for the entire class,
not its individual objects aka class method. Static method invoked by
using class name with dot operator::

   double interestRate = BankAccount.getInterestRate();

Overloaded
   same name diffrent parms

formal parameters
   place holders for actual parameters

Information Hiding and Encapsulation
====================================

class interface
   headings for public methods and public named constants
ADT
   abstract data type
   specification for a set of data and operations on that data
    
UML Class Diagrams
   (+) sign before public methods and instance variables
   (-) sign before private methods and instance variables

   UML Example::

    -------------------------------------------------
    |   Purchase                                    |  <- class name
    -------------------------------------------------
    |   -name:string                                |  <- instace
    |   -groupcount:int                             |       variables
    |   -groupPrice:double                          |
    |   -numberBought:int                           |
    -------------------------------------------------
    |   +setName(string newName):void               |  <- methods
    |   +setPrice(int count):void                   |
    |   +gettotalcost(): double                     |
    -------------------------------------------------
    
Defining an equals method for a class
-------------------------------------

if you do not define one, Java will use a default often not
returning a desired result

.. code-block:: java

    public class Speicies {
        public boolean equals (Species otherObject){
            return (this.name.equalsIgnoreCase(otherObject.name)&&
                    (this.population == otherObject.population)&&
                    (this.growthRate == otherObject.growthRate);
        }
    }

Parameters of a Class Type

.. code-block:: java

    public class DemoSpecies {
        public void tryToReplace(Demospecies otherObject){
            otherObject = this;
        }
    }
    
sending a DemoSpecies object to the method tryToReplace will use
Java's call by value parameter mechanism copies the value of the
object to the formal parameter.

Assignment to the parameter does not affect the argument.
You cannot replace an object passed to it as an argument with
another object.

ArrayList
---------

ArrayList is a parameterized class

Linked list
   contains data and a refrence to another object in the collection.

   ex::

    head -> ["Duey" | -]-> ["cheatem" | null ]
    //node of a linked list, two instace variables data, and refrence

The getLink method of the ListNode class refrences the private instance
variable of a class type. To keep private make ListNode a private inner
class of StringLinkedList.

Inner cass definition local to the outher class definition usable 
anywhere wthin definition of outer class.

I/O for txt files/charecters
============================

creating a PrintWriter object can throw an exception so it must be
inside a try/catch statement.

.. code-block:: java

    PrintWriter out = null;
    try {
        out = new PrintWriter("out.txt");
    }
    catch(FileNotFountException e){
        System.out.print("Fail");
        System.exit(0);
    }

    Scanner reader = new Scanner(System.in);
    int i = reader.nextInt();
    string s1 = reader.nextLine();
    string s2 = reader.nextLine();    

If you enter::

    5 hello
    world

i would equal 5
s1 would equal hello
s2 would equal world

If you enter::

    5
    hello
    world

i would equal 5
s1 would equal "\n"
s2 would equal hello

Adding a reader.nextLine() after the nextInt() will avoid problems.

Scanner class
-------------

=========================       =================================== 
scanner object_name
=========================       ===================================
nextInt()                       reads an int
next()                          reads until delimiter (whitespace)
nextDouble()                    reads double
nextLine()                      reads entire line
useDelimiter(Delim_word)        separator aka delimiter
=========================       ===================================


Strings
=======

- immutable
- charAt(Position/index)
- substring (start, end)

Wrapper Classes
===============

also immutable like string
always require new for instantiation unlike string

.. code-block:: java

    Integer myInteger = new Integer(s);
    
    Integer Class
        int comparTo
        boolean equals
        int intValue
        String toString

Precedence Rules
================

1. unary operators::
   
   +,-,!.++,--

2. binary arithmetic operators::
   
   *,/,%

3. binary arithmetic operators::
   
   +,-

4. boolean operators::
   
   <,>,<=,>=


Conditional Operator
====================

(op1 > op2) ? r1:r2 ;       If (op1>op2) is true do r1, else do r2
    









