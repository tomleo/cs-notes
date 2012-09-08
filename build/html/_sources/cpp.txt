============
C++ Notes
============

c-string
========

array of chars, uses '\0' to end the string

char s[11];                 declares c-string, creates space for 10 chars
    
char s[20] = "Hi There";        declares and initializ c-string
char message[] - "abc";         also acceptable
char message[] = {'a', 'b'}     not acceptable

initializing a c-string does not cause a \n to be inserted

string = "hello";   not llegal assignment opperator does not work with c-string

#include<cstring>               places Hello and \0 into a_string
char a_string[11];
strcpy (a_string, "Hello");     strcopy does not check size of array
                                can write chars beyond declared size
                                causing error
                                
char message[10];
strncpy(message, strvar, 9);    will only copy up to 9 chars
                                avoiding problem with str cpy
                                *will not add '\0' to end
                                
strcmp(str1, str2)              if strings eqal returns 0, if str1 is less
                                returns negative value, if str1 is more 
                                returns positive number
                                
strlen(str)                     returns number of chars in string
strcat(str, "hello")            concats str with "hello"

char str[80]
cin.getline(a, 80)              reads entire line including spaces

cstdlib
========

atoi("1234")        converts to int, if non number char - returns 0
atol                converts to long
atof                converts to double

abs(int)
labs(long)

string
=======

standard string class

getline(cin, line)      entered text assigned to string line
cin.get                 reads one char at a time
getline(cin str, '?')   stops at '?' instead of '\n'
cin.ignore(1000, '\n')  reads upto 1000 chars or to '\n'
str.length()            returns length of string

comparison operators compare the lexicographic order of strings

vector
=======

vectors (like java arrayList)

vector<int> v;          creates vector of ints
v[i] = 42;              can change value at i but not initialize value at i
                        initializing a value this way will not show an error but will cause problems
                        in the program.
v.resize(24)            resizes vector to 24, elements after are lost

Pointer
=======

pointer is memory address of a variable
pointer variables must have a type
    double *p;      declares a pointer to a type double
& operator used to get address of variable
* derefrencing operator
    *p      gets the variable pointed to by p
pointer notation:
    int a, *b;      //notation for pointer
    a = b;
    b = &a;
    cout << b;
    cout << *b;     //derefrencing operator
    
p1 = new int;       //variable can be referred to as *p1

(*head).count = 12;         AND
head -> count = 12;         ARE THE SAME

Linked List
===========

struct ListNode {
    string item;
    int count;
    ListNode *link;     //pointer to another node of type ListNode
};

typedef ListNode* ListNodePtr;
(*head).count = 12;     //head is pointer, *head is the node head points to

dot operator has higher precedence than the dereference operator*, so
parentheses are required

head -> count = 12;     //does the same as (*head).count=12;

ListNodePtr head;       //head points to the first/only node
head = new ListNode   

Basic C++ console
=================

#include<iostream>
using namespace std;
int main() {
    return 0;
}


IO Basics
=========

cout << "Hello";            output to console
cin >> var1;                input from consol
cout << num << "is cool"    output mulitple values
cout << (price + tax);      output arithmetic expressions
<<                          insertion operator

Formatting
----------

cout.precision(5);      number of digits after the decimal point
        
float output/magic formula
cout.setf(ios::fixed);
cout.setf(ios::showpoint);
cout.precision(2);

static_cast<double>(9)  converts 9 to 9.0

fstream
-------

#include<iostream>
#include<fstream>
ifstream fin;
fin.open("input.txt");
fin.close()
ofstream fout;
fout.open("output.txt");
fout.close()

if(fout.fail()){
    cout << "error"
}

Escapes
========

new-line        \n
horizonal tab   \t
alert           \a
backslash       \\
double quote    \"
endl            same as \n but should not be in quotes/strings

Namespace
==========

a collection of names such as cin and cout each name
in a namespace has one specification in the 
namespace

Number Types
============

short
int
long
float
double
long double

Constants
=========

const type_name variable_name;

Enumeration
===========

List of constants of type int
enum Month {JAN, Feb} //JAN value will be set to 0, FEB will be set to 1

Flow of Control
===============

switch(variable){ //switch statement
    case 1:
        cout "do something";
        break;
    case 2:
        cout "do somethin else";
        break;
}

for(n = 1; n<=10; n++){}
    //n is set to one
    //loop continues until statement is false
    //n is incremented at the end of the loop


cmath
========

sqrt(number)
pow(num, power)
fabs(double)        absolute value
ceil(double)        round up
floor(double)       round down


class structure
===============

class name {
    public:
        //vars + defs?
    private:
        //vars + defs?
};
name::method

