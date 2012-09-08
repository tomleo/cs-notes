=============
Scheme Notes
=============

Scheme examples are using the Guile programming lanuage
   Guile is an interpreter and compiler for the Scheme programming language,
   a clean and elegant dialect of Lisp. Guile is up to date with recent Scheme
   [Guile-Documentation]_ 


.. code-block:: scheme

    guile> (boolean? #t)
    #t

    guile> (boolean? "Hello, World!")
    #f

    guile> (symbol? 'xyz)
    #t

    guile> (symbol? 42)
    #f

    guile> (define xyz 9)
    guile> xyz
    9

    guile> (set! xyz #\c)
    guile> xyz
    #\c

    guile> (define x '(1 2 3 4))
    guile> x
    (1 2 3 4)
    guile> (set-car! x 2)
    guile> x
    (2 2 3 4)

caar
   stands for car of car of

cdar
   stands for cdr of car of


.. code-block:: scheme

    guile> (define y (list 1 2 3 4))
    guile> (list-ref y 0)
    1
    guile> (list-ref y 3)
    4
    guile> (list-tail y 1)
    (2 3 4)
    guile> (list-tail y 3)
    (4)

    guile> ((lambda (x) (+ x 2)) 5)
    7

    guile> (define x '(1 2 3))
    guile> (apply + x)
    6

.. [Guile-Documentation] http://www.gnu.org/software/guile/

