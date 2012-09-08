==================
Interview Questions
===================

Amazon
=========

* Difference between linkedlist & array
    Linked list can more easily have data of different sizes
    Arrays are fixed size
    Changing the order of linked list is easier...?
    Lnked List: can interate while changes are happening?
    Linked List: nodes are allocated consecutively in memory improving locality
    of reference and enchances data cache

* Memory fragmentation
    storage space used inefficiently

* Difference between hashtable and hashmap
    Hashtable - null keys/values not allowed
    Hashmap - order may not remain constant

* Count number of 1's in binary representation of integer

def bin(x):
    sign = ''
    if x < 0:
        sign = '-'
    x = abs(x)
    bits = []
    while x:
        #divmod = ((x-x%y)/y, x%y)
        x, rmost = divmod(x, 2)
        #print x, rmost
        bits.append(rmost)
    str_bin = ''.join(str(b) for b in reversed(bits or [0]))
    c = 0
    for t in str_bin:
        if int(t) == 1:
            c+=1
    return c

* merge sorted linked lists

* find prime number in given range

* priorety queue

    Queue ATD aka FIFO Queue

    Highest priorety first
    Enqueue - start at end of line
    Dequeue - exit at from of line



