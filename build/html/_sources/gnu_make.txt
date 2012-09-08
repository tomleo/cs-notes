=================
GNU Make Notes
=================

Rule/Code Structure
===================


Gnu make basic syntax::

    target:	prereq prereq
       commands

target is what must be made,
the prereq's must exist before the target can be created
commands is the shell commands that will create the target from the
prereqs


The following will convert a c file to an object file::

   foo.o:	foo.o foo.h
      gcc -c foo.c


Example with Linking to a system library::

    count_words:   count_words.o lexer.o -lfl
       gcc count_words.o lexer.o -lfl -ocount_words
                    
    count_words.o:	count_words.c
        gcc -c count_words.c
        
    lexer.o: lexer.c
        gcc -c lexer.c
        
    lexer.c: lexer.;
         flex -t lexer.l > lexer.c


- The -l indicates to gcc that a system library must be linked
- fl specifies the name of the library "libfl.a"
- The -l<name> will cause a search for a file in the form libName>so the
  above example should find /usr/lib/libfl.a

Explicit Rules
==============

you can group targets togeather if they have the same prereqs

Example::

   foo.o baz.o: make.h config.h getopt.h

The above code is the same as writing::

   foo.o: make.h config.h getopt.h
   baz.o: make.h config.h getopt.h

Wildcards
---------

Wildcards are the same as the Bourne shell's::

   ~, *, ?, [...], [^...]

?
   any single character

[...]
   a character class
