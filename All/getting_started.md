# 1. Getting Started with Python Language:

- [1. Getting Started with Python Language:](#1-getting-started-with-python-language)
  - [1.1. Getting Started](#11-getting-started)
    - [1.1.1. `Features`](#111-features)
  - [1.2. Installation](#12-installation)
    - [1.2.1. `Verify if Python is installed`](#121-verify-if-python-is-installed)
    - [1.2.2. `Download Python`](#122-download-python)
  - [1.3. Creating Variables and Assigning values](#13-creating-variables-and-assigning-values)
    - [1.3.1. `Rules for variable naming:`](#131-rules-for-variable-naming)
  - [1.4. Indentation](#14-indentation)
  - [1.5. Datatypes](#15-datatypes)
  - [1.6. Collection Types](#16-collection-types)
  - [1.7. User Input](#17-user-input)
  - [1.8. Builtin Modules and Functions](#18-builtin-modules-and-functions)
  - [1.9. Creating Module](#19-creating-module)

1.1. Getting Started
---
- Python is a widely used **high-level programming language** for general-purpose programming.
- Created by **Guido van Rossum** and first released in **1991**.

### 1.1.1. `Features`
- Dynamic type system
- Automatic memory management
- Supports multiple programming paradigms
- Object-Oriented
- Functional Programming
- Procedural styles
- Large and Comprehensive Standard Library.

`Major versions`
- Python 3.x (Current version)
- Python 2.x

1.2. Installation
---
### 1.2.1. `Verify if Python is installed`
- Open Terminal(MAC/ Linux) or Command Prompt(Windows)
- Type 
```console
$ python --version
Python 3.9.6
```
- If you have Python 3.x/ 2.x installed. If not go ahead and download and install latest version of python
### 1.2.2. `Download Python`
`Windows`
- download the latest version of Python 2.7 from the [Official Website](https://www.python.org/downloads/).
- To install it manually, just double-click the file.
-  Installation does automatically modify the PATH environment variable in 3.x but not in 2.x.
- verify once after installation

`macOS`
- As we speak, macOS comes installed with Python 2.7.10, but this version is outdated and slightly modified from the regular Python.
- Install [Homebrew](https://brew.sh/):
```console
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
- Install Python
```console
brew install python3
```


1.3. Creating Variables and Assigning values
---
Syntax:
```python
<variable name> = <value>
```
Example:
```python
a = 2
b = 9223372036854775807
pi = 3.14
name = 'welcome'
x = None
```
Error:
```python
0 = x
#Output: SyntaxError: can't assign to literal
```
### 1.3.1. `Rules for variable naming:`
1. Variables names must start with a letter or an underscore
2. The remainder of your variable name may consist of letters, numbers and underscores.
3. Names are case sensitive

*Assign multiple values to multiple variables*
```python
a, b, c = 1, 2, 3
print(a, b, c)
# Output: 1 2 3
```

1.4. Indentation
---
Python uses the colon symbol (:) and indentation for showing where blocks of code begin and end
Example:
```python
class ExampleClass:
 #Every function belonging to a class must be indented equally
 def __init__(self):
     name = "example"
 def someFunction(self, a): #Notice everything belonging to a function must be indented
    if a > 5:
        return True
    else:
        return False
```
or
```python
#If a function is not indented to the same level it will not be considers as part of the parent class
def separateFunction(b):
    for i in b:
 #Loops are also indented and nested conditions start a new indentation
        if i == 1:
            return True
    return False
separateFunction([2,3,5,6,1])

```

```python
if x > y: y = x
    print(y) # IndentationError: unexpected indent
if x > y: while y != z: y -= 1 # SyntaxError: invalid syntax
```
> An empty block causes an IndentationError. Use pass (a command that does nothing) when you have a block with
no content:
```python
def will_be_implemented_later():
    pass
```

1.5. Datatypes
---

`bool`
- False
- True

A boolean value of either True or False. Logical operations like and, or, not can be performed on booleans.
```python
x or y # if x is False then y otherwise x
x and y # if x is False then x otherwise y
not x # if x is True then False, otherwise True
```
`Numbers`
- `int`: Integer Number
```python
a = 2
b = 100
c = 123456789
d = 38563846326424324
```
- `float`: Floating point Number
```python
a = 2.0
b = 100.e0
c = 123456789.e1
```
- `complex`: Complex Number
```python
a = 2 + 1j
b = 100 + 10j
```
`Strings`
```python
a = 'Welcome'
```
`Testing the type of variables`
- `type`:
```python
a = '123'
print(type(a))  # Out: <class 'str'>
b = 123
print(type(b))  # Out: <class 'int'>
```
- ` isinstance`
```python
i = 7
isinstance(i, int)  # Out: True
```
`Typecasting between datatypes`
```python
a = '123'
b = int(a)
a = '123.456'
b = float(a)
c = int(a) # ValueError: invalid literal for int() with base 10: '123.456'
d = int(b) # 123
```
`Immutable Data Types:`
- `int`, `long`, `float`, `complex`
- `str`
- `bytes`
- `tuple`
- `frozenset`

`Examples of mutable Data Types`:
- `bytearray`
- `list`
- `set`
- `dict`

1.6. Collection Types
---
`Lists`

- The list type is probably the most commonly used collection type in Python. 
- Despite its name, a list is more like an array in other languages, mostly JavaScript.
- List is merely an ordered collection of valid Python values.
- A list can be created by enclosing values, separated by commas, in square brackets:

`Declaring and Assigning values to list: `
```python
int_list = [1, 2, 3]    #list of integers
string_list = ['abc', 'defghi'] #list of strings
empty_list = []         #Empty list
mixed_list = [1, 'abc', True, 2.34, None]   #list of multiple data type
nested_list = [['a', 'b', 'c'], [1, 2, 3]]  #list can contain another list as its element
```
`Accessing list by index: `
```python
names = ['Alice', 'Bob', 'Craig', 'Diana', 'Eric']
print(names[0]) # Alice
print(names[2]) # Craig

#negative index - counting from the end of the list (-1 being the index of the last element).
print(names[-1]) # Eric
print(names[-4]) # Bob

names[0] = 'Ann'
print(names)    # ['Ann', 'Bob', 'Craig', 'Diana', 'Eric']
```
`Add an elements to a list:`
```python
names = ['Alice', 'Bob', 'Craig', 'Diana', 'Eric']
names.append("Sia")
print(names) #['Alice', 'Bob', 'Craig', 'Diana', 'Eric', 'Sia']
```
`Add a new element to list at a specific index:`
```python
names.insert(1, "Nikki")
print(names)    # ['Alice', 'Nikki', 'Bob', 'Craig', 'Diana', 'Eric', 'Sia']
```
`Remove the first occurrence of a value :`
```python
names.remove("Bob")
print(names) # ['Alice', 'Nikki', 'Craig', 'Diana', 'Eric', 'Sia']
```
`Get the index of element in list :`
```python
names.index("Alice") # 0
```
`Count length of list :`
```python
len(names)  # 6
```
`count occurrence of any item in list :`
```python
a = [1, 1, 1, 2, 3, 4]
a.count(1)  # 3
```
`Reverse the list :`
```python
a.reverse()
[4, 3, 2, 1, 1, 1]

# or

a[::-1]
[4, 3, 2, 1, 1, 1]
```
`Remove and return item at index :`
```python
names.pop() # 'Sia'
```
`Iterate over the list elements:`
```python
for element in my_list:
 print (element)
```
`Tuples`

A tuple is similar to a list except that it is fixed-length and immutable.
```python
one_member_tuple = tuple(['Only member'])
ip_address = ('10.20.30.40', 8080)

one_member_tuple = ('Only member',)
#or
one_member_tuple = 'Only member', # No brackets
```
`Dictionary`
- Collection of key-value pairs.
- Surrounded by curly braces
- Each pair is separated by a comma and the key and value are separated by a colon
```python
state_capitals = {
 'Arkansas': 'Little Rock',
 'Colorado': 'Denver',
 'California': 'Sacramento',
 'Georgia': 'Atlanta'
}

#To get a value, refer to it by its key:
ca_capital = state_capitals['California']

#Iterating over a dictionary
for k in state_capitals.keys():
 print('{} is the capital of {}'.format(state_capitals[k], k))
```
`set`
- A set is a collection of elements with no repeats and without insertion order but sorted order
- Defining a set is very similar to defining a dictionary:
```python
first_names = {'Adam', 'Beth', 'Charlie'}

my_list = [1,2,3]
my_set = set(my_list)

#Check membership of the set using in:
if name in first_names:
 print(name)
```

1.7. User Input
---
```python
name = raw_input("What is your name? ") # Out: What is your name? _
name = input("What is your name? ") # Out: What is your name?
```
Example:
```python
x = input("Write a number:")    # Out: Write a number: 10
x / 2   # Out: TypeError: unsupported operand type(s) for /: 'str' and 'int'
float(x) / 2    # Out: 5.0
```
> `Note: It's recommended to use try/except blocks to catch exceptions when dealing with user inputs. For instance, if your code wants to cast a raw_input into an int, and what the user writes is uncastable, it raises a ValueError.`

1.8. Builtin Modules and Functions
---
To check the built in function in python we can use dir(). If called without an argument, return the names in the current scope.
```console
>>> dir(__builtins__)
['ArithmeticError',
 'AssertionError',
 'AttributeError',
 'BaseException',
 'BufferError',
 'BytesWarning',
 'DeprecationWarning',
 'EOFError',
 'Ellipsis',
 'EnvironmentError',
 'Exception',
 'False',
 'FloatingPointError',
 'FutureWarning',
 'GeneratorExit',
 'IOError',
 'ImportError',
 'ImportWarning',
 'IndentationError',
 'IndexError',
 'KeyError',
 'KeyboardInterrupt',
 'LookupError',
 'MemoryError',
 'NameError',
 'None',
 'NotImplemented',
 'NotImplementedError',
 'OSError',
 'OverflowError',
 'PendingDeprecationWarning',
 'ReferenceError',
 'RuntimeError',
 'RuntimeWarning',
 'StandardError',
 'StopIteration',
 'SyntaxError',
 'SyntaxWarning',
 'SystemError',
 'SystemExit',
 'TabError',
 'True',
 'TypeError',
 'UnboundLocalError',
 'UnicodeDecodeError',
 'UnicodeEncodeError',
 'UnicodeError',
 'UnicodeTranslateError',
 'UnicodeWarning',
 'UserWarning',
 'ValueError',
 'Warning',
 'ZeroDivisionError',
 '__debug__',
 '__doc__',
 '__import__',
 '__name__',
 '__package__',
 'abs',
 'all',
 'any',
 'apply',
 'basestring',
 'bin',
 'bool',
 'buffer',
 'bytearray',
 'bytes',
 'callable',
 'chr',
 'classmethod',
 'cmp',
 'coerce',
 'compile',
 'complex',
 'copyright',
 'credits',
 'delattr',
 'dict',
 'dir',
 'divmod',
 'enumerate',
 'eval',
 'execfile',
 'exit',
 'file',
 'filter',
 'float',
 'format',
 'frozenset',
 'getattr',
 'globals',
 'hasattr',
 'hash',
 'help',
 'hex',
 'id',
 'input',
 'int',
 'intern',
 'isinstance',
 'issubclass',
 'iter',
 'len',
 'license',
 'list',
 'locals',
 'long',
 'map',
 'max',
 'memoryview',
 'min',
 'next',
 'object',
 'oct',
 'open',
 'ord',
 'pow',
 'print',
 'property',
 'quit',
 'range',
 'raw_input',
 'reduce',
 'reload',
 'repr',
 'reversed',
 'round',
 'set',
 'setattr',
 'slice',
 'sorted',
 'staticmethod',
 'str',
 'sum',
 'super',
 'tuple',
 'type',
 'unichr',
 'unicode',
 'vars',
 'xrange',
 'zip'
]
```

`help`
- To know the functionality of any function
```console
>>> help(max)
 Help on built-in function max in module __builtin__:
 max(...)
 max(iterable[, key=func]) -> value
 max(a, b, c, ...[, key=func]) -> value
 With a single iterable argument, return its largest item.
 With two or more arguments, return the largest argument.
```
```console
>>> import math
>>> dir(math)
['__doc__', '__name__', '__package__', 'acos', 'acosh',
 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'ceil', 'copysign',
 'cos', 'cosh', 'degrees', 'e', 'erf', 'erfc', 'exp', 'expm1',
 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gamma',
 'hypot', 'isinf', 'isnan', 'ldexp', 'lgamma', 'log', 'log10',
 'log1p', 'modf', 'pi', 'pow', 'radians', 'sin', 'sinh', 'sqrt',
 'tan', 'tanh', 'trunc']
```

1.9. Creating Module
---
- A module is an importable file containing definitions and statements
- A module can be created by creating a .py file.
```python
# hello.py
def say_hello():
 print("Hello!")
```
Importing module
```python
# greet.py
import hello
hello.say_hello()
```
Specific functions of a module can be imported.
```python
# greet.py
from hello import say_hello
say_hello()
```
