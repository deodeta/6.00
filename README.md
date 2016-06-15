# Lecture 02 | Core Elements of a Program

A program is a script that consists of a sequence of commands, each command telling the interpreter to do a specific thing.

## [IDLE](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=69)

IDLE is an **IDE (Integrated Development Environment)** built for Python. Characteristics of an IDE:-
* Specialized Text Editor
* Highlighting
* Autocompletion
* Smartindent
* It also comes with a **Shell** which is the environment that actually interprets the Python code (with syntax highlighting).
* Integrated Debugger, print statements are our friend.

When you type an expression into the shell the expression is evaluated and the value is printed.
When the interpreter executes a script containing expressions, the expressions are also first evaluated, but the values will not be displayed on the screen (unless you explicitly use the "print" function).

## [Object](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=233)

At the core of Python are `Objects`. Basically everything in Python is an object, even Python code itself (as a program is simply treated as data on a stored program computer). Each Object has a `type`.
Types are classifications of objects (what Python as an object oriented programming lanugage deals with). They determine how these objects (or rather the strings representing these objects) are dealt with. In short, an object's type determines:
* the kind of object it is
* what can be done with the object (what operations can be performed on/with it)
For example, adding two integer objects will result in an integer object (int + int = int), whereas adding two string objects will concatenate both strings, resulting in another string object (str + str = str).
However, adding an integer object to a string object will result in an error:
TypeError: unsupported operand type(s) for +: 'int' and 'str', as this operation can not be performed on objects of these types.

### Type of Objects 
One can use the built-in function `type()`, to find the type of an object. Object types can be classed into two fundamental categorys :- 
* **Scalar**:  These tpyes are indivisible, i.e. basic types which can not be created from any other types and can not be decomposed e.g. integers. They are sometimes referred to as the "atoms of the programming language".
* **Non Scalar**: These types can be decomposed e.g. strings.

#### [Scalar](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=323)
The following are the **scalar type**.

* [Integer](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=365)
Integers in Python are of the type `int`.
For every type there is the notion of a **literal**. A literal is a notation for representing a fixed value in source code. 
Almost all programming languages have notations for atomic values such as integers, floating-point numbers, and strings, and usually for booleans and characters; some also have notations for elements of enumerated types and compound values such as arrays, records, and objects. 
In contrast to literals, variables or constants are symbols that can take on one of a class of fixed values, the constant being constrained not to change. Literals are often used to initialize variables.
ex:-   
````
3
````
When we check the `type` of the object represented by the literal `3` ...  
````
type(3)
````
it will return  
````
<type 'int'>
````
The type of the object represented by the literal `3` is therefore `int` - an integer.

* [Float](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=425)

Floats are used to represent **real numbers**.
ex:- 
````
3.2
````
check the `type` of the object represented by the literal `3.2`  
````
type(3.2)
````
it will return 
````
<type 'float'>
````

Interestingly, in Python, the object represented by the literal `3` is of type `int`, whereas the object denoted by the literal `3.0` is a `float`.

**NOTE:- ** 
* Floats do not behave exactly like 'real numbers' - they are only approximations of them. This is not a real problem most of the time (see later lectures).

* [Boolean](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=532)

Booleans can only take one of two values.
* `True`, `type(True)` therefore returns `<type 'bool'>`
* `False`

* [None](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=584)

An object can also take on the value `None`. The `type` of that object would then be `<type 'NoneType'>`. The `None` value/type is mostly used when one wants to only temporarily assign a value to a variable.

#### Non Scalar

* [String](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=630)
Python does not have a fundamental type for characters called `char`, as available in other programming languages. 
Strings (type `str`) of characters (length = 1) are used to represent these e.g. the strings 'a' or "a" to represent the character 'a'.
ex:-
````
'a'
````
when we check the `type` of `'a'` we get  
````
<type 'str'>
````

Objects of type `str` can be denoted using literals that contain either `' '` or `""`.

## [Expression](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=738)

* **Expression:-** An expression is composed of objects, more specifically operands, and operators. An Expression can furthermore be interpreted into a value. In short, an expression is a sequence of operands (objects) and operators.

### Operators 

ex:- 
````
3 + 2
````
evaluates to `5` 

````
3/2
````
`/` is the **division operator**. The expression above evalutes to `1`, however

````
3.0/2.0
````
evaluates to `1.5`.

**NOTE:-**
* Division operator `/` on two objects of type `int` returns an object of type `int` (integer division) - not in Python 3.0. If at least one of the operands is a `float`, the expression will also evaluate to an object of type `float`.

* In Python 3.0 use the operator `//` for integer division.

### [Overloading](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=861)

Consider this example, 
````
'a' + 'b'
````
returns `"ab"`

The operator `+` is **overloaded**.  **Overloaded Operators** have a meaning that depends upon the types of operands. The example above displays the concatenation of two strings using the `+` operator.

### [Type Conversion ](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=961)
Python does some type checking.

The code below
````
'a' + 3
````
produces a **static semantic error**. The expression is syntactically correct (operand - operator - operand), but it is not meaningful, as one can not concatenate `str` and `int` objects. More precise, the error is a TypeError:

````
>>> 'a' + 3
Traceback (most recent call last):
  File "<string>", line 1, in <module>
TypeError: cannot concatenate 'str' and 'int' objects

````
Type checking is useful for a programming languages, as it prevents the programmer from trying something error prone.

The code above needs to be modified to concatenate the two objects.

````
'a' + '3'   //here '3' is a string literal
````

we can also do this:

````
'a' + str(3)    //use type name as conversion function to attempt type conversion, here: converting the integer 3 into the string '3'

int('3')        //converting string '3' into the integer 3
````
the code below will generate a static semantic error:  

````
int('0.0')
````

the error is: 

````
>>> int('0.0')
Traceback (most recent call last):
  File "<string>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '0.0'
````
This however is a valid type conversion:

````
int(2.1)        //will evaluate to the integer 2

In short, a type conversion converts the type of an object from one type into another, e.g. applying str() to the integer 3 results in the string '3'.
````

## [Commands](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=1462)
**Programs or Scripts**: are sequences of commands, each commands telling the interpreter to do a specific thing.  
ex:- 
````
print type(5.6)
````

### [Variables](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=1500)

A variable is a name for an object, used to refer to that object (e.g. within code). You can not use Python keywords (words with a special meaning within the programming language) as names.

### [Assignment](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=1495)
Consider this example: 

````
x = 3
````
The above expression is an **assignment** statement, with `x` as a **variable**.

An **assignment** statement binds a name to an object.

## [Input](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=1682)
To get an input (e.g. from a keyboard) we use the function `raw_input()`
There are two type of input statement in Python 2.x, 


### Raw Input
`raw_input()` - the only input function present in Python 3. Stick to this one!
### Input 

The function raw_input() returns a string, whereas in Python 2.x the function input() evaluates the input in the execution context in which it is called (treats any input as Python code and tries to execute it).

## [Straight line and branching programs](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=1888)

All the programs so far were **Straight Line Program**. In these,the sequence of commands is executed one after another. Every command is therefore executed exactly once.
The number of statements or commands governs the length of time a straight line program runs for, as every command is executed exactly once. The length of time a straight line program runs for is therefore not related to the input or the size of the data evaluated, but to the number of lines of code.
However, for interesting programs we need branching programs that include tests. With these, the sequence of commands will be executed differently, depending on conditions set within the program.
The most primitive of such tests is a conditional statement.

### [Conditional Statement](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=1997)
Conditional statements are used to control flow of commands executed. A conditional statement starts with an `if` statement and can also include `elif` and `else` statements:
* `if`
* `else`
* `elif` : else if


ex:-

````
if x%2 == 0:
    print "Even"
else:
    print "Odd"    
````
The operator `==` is used to do a comparison (NOT assignment operator).

### [Nesting ](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=2167)
We can also nest one conditional statement inside another...:- 

````
if x%2 == 0:
    print "Even"
else:
    if x % 3 != 0
        print "Hello"
    print "Odd"    
````
Here is how an `if` constructs works:-
* Evaluates the condition, if true: executes the `if` block,
* If false: `else` block is executed
* Either the `if` block or the `else` block is executed, but never both.

In a branching program, each command/instruction is executed at most once. Therefore, the length of time required to run a program is governed strictly by the size of the program (number of commands).
Both straight line programs and branching programs are not proportional (in fact independent) in time to the input. Therefore, they are limited in what they can do (calculating GPA of MIT students should take less time than calculating the GPA of students of a bigger university).
This is why we need looping constructs.

### [Indentation ](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=2220)
Indentation is very important in Python. The visual structure follows the semantic structure. 

## [Looping constructs](https://www.youtube.com/watch?v=SLvTCHhu5SE&list=PLB2BE3D6CA77BB8F7#t=2729)

Allow iteration.
Once we add loops to a programming language, it becomes **Turing Complete** (every program that can be computed can be computed with this programming language). The concept of loops is **iteration**.  
With loops, we can achieve a more complicated flow of control, as we can execute a statement more than once.

Here is a simple loop:

````
while ans*ans*ans < abs(x):
    ans = ans + 1
````




## References
### Links
1. [MIT OCW](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-00sc-introduction-to-computer-science-and-programming-spring-2011/unit-1/lecture-2-core-elements-of-a-program/)
2. [Lecture code handout (PDF)](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-00sc-introduction-to-computer-science-and-programming-spring-2011/unit-1/lecture-2-core-elements-of-a-program/MIT6_00SCS11_lec02.pdf)
3. [Lecture code (PY)](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-00sc-introduction-to-computer-science-and-programming-spring-2011/unit-1/lecture-2-core-elements-of-a-program/lec02.py)

### Problem Sets
1. Problem Set 0: Introduction to Python and IDLE (Due)
    1. [Problem Set 0](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-00sc-introduction-to-computer-science-and-programming-spring-2011/unit-1/lecture-2-core-elements-of-a-program/MIT6_00SCS11_ps0.pdf)
2. Problem Set 1 (Assigned)
    1. [Problem Set 1 Due on Lecture 4](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-00sc-introduction-to-computer-science-and-programming-spring-2011/unit-1/lecture-4-machine-interpretation-of-a-program/)

## Check Yourself
### What is a 'type'?

Types are classifications of objects, which is what Python, as an OOP language, deals with. They determine how those objects are dealt with (for example, adding two integers results in an integer, two strings results in a concatenated string, and an integer and a string results in an error).

### What is an 'expression'?

An expression is composed of objects (or operands) and operators, and can be interpreted into a value.

### What is a type conversion?

A type conversion turns one type of object into another. For example, applying str to the integer 3 results in the string '3'.

### What is a keyword?

Keywords are words that have special meanings within a language. Many editors will display them in special colors. These words cannot be used as variables.

### What is the difference between a straight line program and a branching program?

A straight line program simply goes through and carries out each step. A branching program will do different things depending on conditions set within the program.

### What is a conditional? 

A conditional statement starts with an if statement, and can also include elif and else statements.
