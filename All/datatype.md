# 1. Python Data Types

- [1. Python Data Types](#1-python-data-types)
  - [1.1. String](#11-string)
    - [1.1.1. String Functions](#111-string-functions)
    - [1.1.2. String Useful constants](#112-string-useful-constants)
    - [1.1.3. Stripping String](#113-stripping-string)
    - [1.1.4. Reversing String](#114-reversing-string)
    - [1.1.5. Split a String](#115-split-a-string)
    - [1.1.6. Replace all occurrences of one substring with another substring](#116-replace-all-occurrences-of-one-substring-with-another-substring)
    - [1.1.7. Testing what a string is composed of](#117-testing-what-a-string-is-composed-of)
    - [1.1.8. String contains](#118-string-contains)
    - [1.1.9. Join a list of Strings into one string](#119-join-a-list-of-strings-into-one-string)
    - [1.1.10. Counting number of times a substring appears in a string](#1110-counting-number-of-times-a-substring-appears-in-a-string)
  - [1.2. List](#12-list)
    - [1.2.1. List Method](#121-list-method)
    - [1.2.2. Accessing List values](#122-accessing-list-values)
    - [1.2.3. Checking if list is empty](#123-checking-if-list-is-empty)
    - [1.2.4. Iterating over a list](#124-iterating-over-a-list)
    - [1.2.5. Checking whether an item is in a list](#125-checking-whether-an-item-is-in-a-list)
    - [1.2.6. Any and All](#126-any-and-all)
    - [1.2.7. Reversing list elements](#127-reversing-list-elements)
    - [1.2.8. Concatenate and Merge lists](#128-concatenate-and-merge-lists)
    - [1.2.9. Length of a list](#129-length-of-a-list)
    - [1.2.10. Remove duplicate values in list](#1210-remove-duplicate-values-in-list)
    - [1.2.11. Comparison of lists](#1211-comparison-of-lists)
    - [1.2.12. Accessing values in nested list](#1212-accessing-values-in-nested-list)
    - [1.2.13. Initializing a List to a Fixed Number of Elements](#1213-initializing-a-list-to-a-fixed-number-of-elements)
  - [1.3. Set](#13-set)
    - [1.3.1. Operations on Sets](#131-operations-on-sets)
    - [1.3.2. Unique elements of a list](#132-unique-elements-of-a-list)
    - [1.3.3. Set of Sets](#133-set-of-sets)
    - [1.3.4. Set Operations using Methods and Builtins](#134-set-operations-using-methods-and-builtins)
  - [1.4. Dictionary](#14-dictionary)
    - [1.4.1. Introduction](#141-introduction)
    - [1.4.2. Creating a dictionary](#142-creating-a-dictionary)
    - [1.4.3. Avoiding KeyError Exceptions](#143-avoiding-keyerror-exceptions)
    - [1.4.4. Iterating Over a Dictionary](#144-iterating-over-a-dictionary)
    - [1.4.5. Accessing keys and values](#145-accessing-keys-and-values)
    - [1.4.6. The trailing comma](#146-the-trailing-comma)
    - [1.4.7. The dict() constructor](#147-the-dict-constructor)
  - [1.5. Tuple](#15-tuple)
    - [1.5.1. Tuple](#151-tuple)
    - [1.5.2. Tuples are immutable](#152-tuples-are-immutable)
    - [1.5.3. Built-in Tuple Functions](#153-built-in-tuple-functions)
    - [1.5.4. Indexing Tuples](#154-indexing-tuples)
    - [1.5.5. Reversing Elements](#155-reversing-elements)


1.1. String
---
### 1.1.1. String Functions
Python's string type provides many functions

- str.upper
- str.lower
- str.capitalize
- str.title
- str.swapcase
- str.format
- f-string

`str.upper()` 

**str.upper** takes every character in a string and converts it to its uppercase equivalent, for example:
```python
"This is a string.".upper()  # "THIS IS A STRING."

str.upper("This is a string") # "THIS IS A STRING"

map(str.upper,["These","are","some","'strings'"]) # ['THESE', 'ARE', 'SOME', "'STRINGS'"]

```

`str.lower()`

str.lower does the opposite; it takes every character in a string and converts it to its lowercase equivalent:
```python
"This IS a string.".lower() # "this is a string."
```

`str.capitalize()`

str.capitalize returns a capitalized version of the string, that is, it makes the first character have upper case and
the rest lower:

```python
"this Is A String.".capitalize()  # "This is a string."
```

`str.title()`
str.title returns the title cased version of the string, that is, every letter in the beginning of a word is made upper
case and all others are made lower case:

```python
"this Is a String".title()  # "This Is A String"
```

`str.swapcase()`

str.swapcase returns a new string object in which all lower case characters are swapped to upper case and all
upper case characters to lower:

```python
#Swaps case of each character
"this iS A STRiNG".swapcase() # "THIS Is a strIng"
```

`str.format() and f-strings`

Given the following variables:
```python
i = 10
f = 1.5
s = "foo"
l = ['a', 1, 2]
d = {'a': 1, 2: 'foo'}
```
The following statements are all equivalent
```console
"10 1.5 foo ['a', 1, 2] {'a': 1, 2: 'foo'}"
>>> "{} {} {} {} {}".format(i, f, s, l, d)
>>> str.format("{} {} {} {} {}", i, f, s, l, d)
>>> "{0} {1} {2} {3} {4}".format(i, f, s, l, d)
>>> "{0:d} {1:0.1f} {2} {3!r} {4!r}".format(i, f, s, l, d)
>>> "{i:d} {f:0.1f} {s} {l!r} {d!r}".format(i=i, f=f, s=s, l=l, d=d)
>>> f"{i} {f} {s} {l} {d}"
>>> f"{i:d} {f:0.1f} {s} {l!r} {d!r}"
```

### 1.1.2. String Useful constants

- string.ascii_letters
- string.ascii_lowercase
- string.ascii_uppercase
- string.digits
- string.hexdigits
- string.octaldigits
- string.punctuation
- string.whitespace
- string.printable
  

`Import the string module`
```console
>>> import string
```

`string.ascii_letters:`
Concatenation of ascii_lowercase and ascii_uppercase:
```console
>>> string.ascii_letters
'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'
```

`string.ascii_lowercase:`
Contains all lower case ASCII characters:
```console
>>> string.ascii_lowercase
'abcdefghijklmnopqrstuvwxyz'
```
`string.ascii_uppercase:`
Contains all upper case ASCII characters:
```console
>>> string.ascii_uppercase
'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
```
`string.digits:`
Contains all decimal digit characters:
```console
>>> string.digits
'0123456789'
```
`string.hexdigits:`
Contains all hex digit characters:
```console
>>> string.hexdigits
'0123456789abcdefABCDEF'
```
`string.octaldigits:`
Contains all octal digit characters:
```console
>>> string.octaldigits
'01234567'
```
`string.punctuation:`
Contains all characters which are considered punctuation in the C locale:
```console
>>> string.punctuation
'!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~'
```
`string.whitespace:`
Contains all ASCII characters considered whitespace:
```console
>>> string.whitespace
' \t\n\r\x0b\x0c'
```
`string.printable:`
Contains all characters which are considered printable; a combination of string.digits, string.ascii_letters,
string.punctuation, and string.whitespace.
```console
>>> string.printable
'0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~\t\n\r\x0b\x0c'
```

### 1.1.3. Stripping String
`str.strip()`
```console
>>> "       a line with leading and trailing space ".strip()
'a line with leading and trailing space'
```
```console
>>> ">>> a Python prompt".strip('> ') # strips '>' character and space character
'a Python prompt'
```

`str.rstrip()`
```console
>>> "       spacious string     ".rstrip()
'       spacious string'
```

`str.lstrip()`
```console
>>> "       spacious string     ".rstrip()
'spacious string        '
```

### 1.1.4. Reversing String

`reversed()`
```console
>>> reversed('hello')
<reversed object at 0x0000000000000000>

>>> [char for char in reversed('hello')]
['o', 'l', 'l', 'e', 'h']
```
```console
>>> ''.join(reversed('hello'))
'olleh'
```

> While using `reversed()` might be more readable to uninitiated Python users, using extended slicing with a step of
-1 is faster and more concise. Here , try to implement it as function:
```console
>>> def reversed_string(main_string):
... return main_string[::-1]
...
>>> reversed_string('hello')
'olleh'
```

### 1.1.5. Split a String
`str.split(sep=None, maxsplit=-1)`

```console
#Splitted by spaces
>>> "This is a sentence.".split()
['This', 'is', 'a', 'sentence.']

>>> " This is a sentence. ".split()
['This', 'is', 'a', 'sentence.']

>>> "           ".split()
[]
```
```console
#Splitted by sep
>>> "This is a sentence.".split(' ')
['This', 'is', 'a', 'sentence.']

>>> "Earth,Stars,Sun,Moon".split(',')
['Earth', 'Stars', 'Sun', 'Moon']

>>> " This is       a sentence. ".split(' ')
['', 'This', 'is', '', '', '', 'a', 'sentence.', '', '']

>>> "This is a sentence.".split('e')
['This is a s', 'nt', 'nc', '.']

>>> "This is a sentence.".split('en')
['This is a s', 't', 'ce.']

```
> The default is to split on every occurrence of the delimiter,however the maxsplit parameter limits the number of splittings that occur. The default value of -1 means no limit:

```console
>>> "This is a sentence.".split('e', maxsplit=0)
['This is a sentence.']

>>> "This is a sentence.".split('e', maxsplit=1)
['This is a s', 'ntence.']

>>> "This is a sentence.".split('e', maxsplit=2)
['This is a s', 'nt', 'nce.']

>>> "This is a sentence.".split('e', maxsplit=-1)
['This is a s', 'nt', 'nc', '.']
```
### 1.1.6. Replace all occurrences of one substring with another substring
`str.replace(old,new[,count])`
```console
>>> "Make sure to foo your sentence.".replace('foo', 'spam')
"Make sure to spam your sentence."

>>> "It can foo multiple examples of foo if you want.".replace('foo', 'spam')
"It can spam multiple examples of spam if you want."
```
unless, of course, we supply a value for count. In this case count occurrences are going to get replaced:
```console
>>> """It can foo multiple examples of foo if you want, \
... or you can limit the foo with the third argument.""".replace('foo', 'spam', 1)
'It can spam multiple examples of foo if you want, or you can limit the foo with the third
argument.'
```

### 1.1.7. Testing what a string is composed of
 
  - string.isalpha
  - string.isupper
  - string.islower
  - string.istitle
  - string.isdecimal
  - string.isdigit
  - string.isnumeric
  - string.isalnum
  - string.isspace

`string.isalpha()`
```console
>>> "Hello World".isalpha() # contains a space
False

>>> "Hello2World".isalpha() # contains a number
False

>>> "HelloWorld!".isalpha() # contains punctuation
False

>>> "HelloWorld".isalpha()
True
```
`string.isupper()`
```console
>>> "HeLLO WORLD".isupper()
False

>>> "HELLO WORLD".isupper()
True

>>> "".isupper()
False
```
`string.islower()`
```console
>>> "Hello world".islower()
False

>>> "hello world".islower()
True

>>> "".islower()
False
```
`string.istitle()`
```console
>>> "hello world".istitle()
False
>>> "Hello world".istitle()
False
>>> "Hello World".istitle()
True
>>> "".istitle()
False
```
`string.isdecimal` `string.isdigit` `string.isnumeric`

|  | isdecimal | isdigit | isnumeric |
| :---: | :---: | :---: | :---:|
| 12345| `True`| `True`| `Tru`e|
| ?2??5| `True`| `True`| `True`|
| ?²³?????| `False`| `True`| `True`|
| ??| `false`| `False`| `True`|
| Five| `False`| `False`| `False`|

`string.isalnum()`
```console
>>> "Hello2World".isalnum()
True
>>> "HelloWorld".isalnum()
True
>>> "2016".isalnum()
True
>>> "Hello World".isalnum() # contains whitespace
False
```
`string.isspace()`
```console
>>> "".isspace()
False
```

### 1.1.8. String contains
To check if a string contains a given substring. Just use the `in` operator:
```console
>>> "foo" in "foo.baz.bar"
True
```
> Note: testing an empty string will always result in True:
```console
>>> "" in "test"
True
```

### 1.1.9. Join a list of Strings into one string
A string can be used as a separator to join a list of strings together into a single string using the `join()` method.
```console
>>> " ".join(["once","upon","a","time"])
"once upon a time"

>>> "---".join(["once", "upon", "a", "time"])
"once---upon---a---time"

```
### 1.1.10. Counting number of times a substring appears in a string
`str.count()`
```python
str.count(sub[, start[, end]])
```
```console
>>> s = "She sells seashells by the seashore."
>>> s.count("sh")
2
>>> s.count("se")
3
>>> s.count("sea")
2
>>> s.count("seashells")
1
```

1.2. List
---

### 1.2.1. List Method
  - list.append
  - list.extend
  - list.index
  - list.insert
  - list.pop
  - list.remove
  - list.reverse
  - list.count
  - list.sort
  - list.clear

`list.append(value)` – appends a new element to the end of the list.
```python
a = [1, 2, 3, 4, 5]
a.append(6) # a: [1, 2, 3, 4, 5, 6]
a.append(7) # a: [1, 2, 3, 4, 5, 6, 7]
a.append(7) # a: [1, 2, 3, 4, 5, 6, 7, 7]

# Append another list
b = [8, 9]
a.append(b) # a: [1, 2, 3, 4, 5, 6, 7, 7, [8, 9]]

my_string = "hello world"
a.append(my_string) # a: [1, 2, 3, 4, 5, 6, 7, 7, [8, 9], "hello world"]
```
> Note that the append() method only appends one new element to the end of the list. If you append a list to another list, the list that you append becomes a single element at the end of the first list.
```python
# Appending a list to another list
a = [1, 2, 3, 4, 5, 6, 7, 7]
b = [8, 9]
a.append(b) # a: [1, 2, 3, 4, 5, 6, 7, 7, [8, 9]]
a[8]  # Returns: [8,9]
```
`list.extend(enumerable/iterable)` – extends the list by appending elements from another enumerable
```python
a = [1, 2, 3, 4, 5, 6, 7, 7]
b = [8, 9, 10]
a.extend(b) # a: [1, 2, 3, 4, 5, 6, 7, 7, 8, 9, 10]

a.extend(range(3))  # a: [1, 2, 3, 4, 5, 6, 7, 7, 8, 9, 10, 0, 1, 2]
```
> Lists can also be concatenated with the + operator. Note that this does not modify any of the original lists:
```python
a = [1, 2, 3, 4, 5, 6] + [7, 7] + b
# a: [1, 2, 3, 4, 5, 6, 7, 7, 8, 9, 10]
```
`list.index(value, [startIndex])` 
- Gets the index of the first occurrence of the input value.
- If the input value is not in the list a ValueError exception is raised.
- If a second argument is provided, the search is started at that specified index.

```python
a.index(7)  # Returns: 6
a.index(49) # ValueError, because 49 is not in a.
a.index(7, 7) # Returns: 7
a.index(7, 8) # ValueError, because there is no 7 starting at index 8
```
`list.insert(index, value)` – inserts value just before the specified index.

Thus after the insertion the new
element occupies position index.
```python
a.insert(0, 0) # insert 0 at position 0
a.insert(2, 5) # insert 5 at position 2
# a: [0, 1, 5, 2, 3, 4, 5, 6, 7, 7, 8, 9, 10]
```
`list.pop([index])` – removes and returns the item at index. With no argument it removes and returns the last
element of the list.
```python
a.pop(2)  # Returns: 5
# a: [0, 1, 2, 3, 4, 5, 6, 7, 7, 8, 9, 10]

a.pop(8)  # Returns: 7
# a: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# With no argument:
a.pop() # Returns: 10
# a: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
`list.remove(value)` – removes the first occurrence of the specified value.

If the provided value cannot be found, a
ValueError is raised.
```python
a.remove(0)
a.remove(9)   # a: [1, 2, 3, 4, 5, 6, 7, 8]
a.remove(10)  # ValueError, because 10 is not in a
```
`list.reverse()` - reverses the list in-place and returns None.
```python
a.reverse()
# a: [8, 7, 6, 5, 4, 3, 2, 1]
```

`list.count(value)` - counts the number of occurrences of some value in the list.
```python
a.count(7)
# Returns: 2
```
`list.sort`
```python
a.sort()  # a = [1, 2, 3, 4, 5, 6, 7, 8]
# Sorts the list in numerical order
```
Lists can also be reversed when sorted using the **reverse=True** flag in the sort() method.
```python
a.sort(reverse=True)
# a = [8, 7, 6, 5, 4, 3, 2, 1]
```
`list.clear()` – removes all items from the list 
```python
a.clear()
# a = []
```
`Replication` – multiplying an existing list by an integer will produce a larger list consisting of that many copies of the original. This can be useful for example for list initialization:

```python
b = ["blah"] * 3
# b = ["blah", "blah", "blah"]

b = [1, 3, 5] * 5
# [1, 3, 5, 1, 3, 5, 1, 3, 5, 1, 3, 5, 1, 3, 5]
```
`Element deletion` – it is possible to delete multiple elements in the list using the del keyword and slice
notation:
```python
a = list(range(10))
del a[::2]  # a = [1, 3, 5, 7, 9]
del a[-1]   # a = [1, 3, 5, 7]
del a[:]    # a = []
```

### 1.2.2. Accessing List values
> Python lists are zero-indexed, and act like arrays in other languages.
`Index`
```python
lst = [1, 2, 3, 4]
lst[0] # 1
lst[1] # 2

lst[4] # IndexError: list index out of range
```
Negative indices are interpreted as counting from the end of the list
```python
lst[-1] # 4
lst[-2] # 3

lst[-5] # IndexError: list index out of range
```
`Slice notation as list[start:end:step]`
```python
lst[1:] # [2, 3, 4]
lst[:3] # [1, 2, 3]
lst[::2] # [1, 3]
lst[::-1] # [4, 3, 2, 1]
lst[-1:0:-1] # [4, 3, 2]
lst[5:8] # [] since starting index is greater than length of lst, returns empty list
lst[1:10] # [2, 3, 4] same as omitting ending index

#reversing list
lst[::-1] # [4, 3, 2, 1]

lst[3:1:-1] # [4, 3]
```

### 1.2.3. Checking if list is empty
> The emptiness of a list is associated to the boolean False, so you don't have to check `len(lst) == 0`, but just `lst` or `not lst`
```python
lst = []
if not lst:
 print("list is empty")
# Output: list is empty
```
### 1.2.4. Iterating over a list
`for loop`
```python
my_list = ['foo', 'bar', 'baz']
for item in my_list:
  print(item)

# Output: foo
# Output: bar
# Output: baz
```
You can also get the position of each item at the same time:
```python
for (index, item) in enumerate(my_list):
  print('The item in position {} is: {}'.format(index, item))

# Output: The item in position 0 is: foo
# Output: The item in position 1 is: bar
# Output: The item in position 2 is: baz
```
The other way of iterating a list based on the index value:
```python
for i in range(0,len(my_list)):
  print(my_list[i])

#output:  foo
#output:  bar
#output:  baz
```
### 1.2.5. Checking whether an item is in a list
`in`
```python
lst = ['test', 'twest', 'tweast', 'treast']
'test' in lst
# Out: True

'toast' in lst
# Out: False

```
### 1.2.6. Any and All
`all()` - Determine if all the values in an iterable evaluate to True
```python
nums = [1, 1, 0, 1]
all(nums) # False

chars = ['a', 'b', 'c', 'd']
all(chars)  # True
```

`any()` - Determines if one or more values in an iterable evaluate to True
```python
nums = [1, 1, 0, 1]
any(nums) # True

vals = [None, None, None, False]
any(vals) # False
```
### 1.2.7. Reversing list elements
`reversed()`
```python
numbers = [4, 1, 3, 2, 6, 5, 8, 7, 9]
rev = reversed(numbers)
# rev = [9, 8, 7, 6, 5, 4, 3, 2, 1]
```
### 1.2.8. Concatenate and Merge lists
> merged = list1 + list2
```python
for a, b in zip(alist, blist):
  print(a, b)

# Output:
# a1 b1
# a2 b2
# a3 b3

```
### 1.2.9. Length of a list
`len()` - Get the one-dimensional length of a list.
```python
len(['one', 'two']) # returns 2
len(['one', [2, 3], 'four']) # returns 3, not 4
```
> `len()` also works on `strings`, `dictionaries`, and other data structures similar to lists 

> Note that `len()` is a built-in function, not a method of a list object.
 
> Cost of len() is O(1),
### 1.2.10. Remove duplicate values in list
Removing duplicate values in a list can be done by converting the list to a `set` 
```python
names = ["aixk", "duke", "edik", "tofp", "duke"]
list(set(names))  # Out: ['duke', 'tofp', 'aixk', 'edik']
```
### 1.2.11. Comparison of lists

```python
[1, 10, 100] < [2, 10, 100]
# True, because 1 < 2

[1, 10, 100] < [1, 10, 100]
# False, because the lists are equal

[1, 10, 100] <= [1, 10, 100]
# True, because the lists are equal

[1, 10, 100] < [1, 10, 101]
# True, because 100 < 101

[1, 10, 100] < [0, 10, 100]
# False, because 0 < 1
```
### 1.2.12. Accessing values in nested list

```python
alist = [[[1,2],[3,4]], [[5,6,7],[8,9,10], [12, 13, 14]]]

print(alist[0][0][1]) #2
#Accesses second element in the first list in the first list

print(alist[1][1][2]) #10
#Accesses the third element in the second list in the second list
```
`nested for loops`
```python
alist = [[1, 2, 11],[3, 4], [5, 6, 7], [8, 9, 10],[12, 13, 14]]
for row in alist: #One way to loop through nested lists
  for col in row:
    print(col)

#[1, 2, 11]
#[3, 4]
#[5, 6, 7]
#[8, 9, 10]
#[12, 13, 14]

```
### 1.2.13. Initializing a List to a Fixed Number of Elements

```python
my_list = [None] * 10
#[None, None, None, None, None, None, None, None, None, None]

my_list = ['test'] * 10
#['test', 'test', 'test', 'test', 'test', 'test', 'test', 'test', 'test', 'test']
```

1.3. Set
---
### 1.3.1. Operations on Sets
`with other sets`
```python
# Intersection
{1, 2, 3, 4, 5}.intersection({3, 4, 5, 6}) # {3, 4, 5}
{1, 2, 3, 4, 5} & {3, 4, 5, 6} # {3, 4, 5}

# Union
{1, 2, 3, 4, 5}.union({3, 4, 5, 6}) # {1, 2, 3, 4, 5, 6}
{1, 2, 3, 4, 5} | {3, 4, 5, 6} # {1, 2, 3, 4, 5, 6}

# Difference
{1, 2, 3, 4}.difference({2, 3, 5}) # {1, 4}
{1, 2, 3, 4} - {2, 3, 5} # {1, 4}

# Symmetric difference with
{1, 2, 3, 4}.symmetric_difference({2, 3, 5}) # {1, 4, 5}
{1, 2, 3, 4} ^ {2, 3, 5} # {1, 4, 5}

# Superset check
{1, 2}.issuperset({1, 2, 3}) # False
{1, 2} >= {1, 2, 3} # False

# Subset check
{1, 2}.issubset({1, 2, 3}) # True
{1, 2} <= {1, 2, 3} # True

# Disjoint check
{1, 2}.isdisjoint({3, 4}) # True
{1, 2}.isdisjoint({1, 4}) # False
```
`with single elements`
```python
# Existence check
2 in {1,2,3} # True
4 in {1,2,3} # False
4 not in {1,2,3} # True

# Add and Remove
s = {1,2,3}
s.add(4) # s == {1,2,3,4}
s.discard(3) # s == {1,2,4}
s.discard(5) # s == {1,2,4}
s.remove(2) # s == {1,4}
s.remove(2) # KeyError!
```
### 1.3.2. Unique elements of a list

```python
restaurants = ["McDonald's", "Burger King", "McDonald's", "Chicken Chicken"]
unique_restaurants = set(restaurants)
print(unique_restaurants)
# prints {'Chicken Chicken', "McDonald's", 'Burger King'}
```
```python
list(unique_restaurants)
# ['Chicken Chicken', "McDonald's", 'Burger King']
```
```python
# Removes all duplicates and returns another list
list(set(restaurants))
```
### 1.3.3. Set of Sets

```python
{{1,2}, {3,4}}
```
leads to:
```python
TypeError: unhashable type: 'set'
```
Instead, use `frozenset`:
```python
{frozenset({1, 2}), frozenset({3, 4})}
```
### 1.3.4. Set Operations using Methods and Builtins
`sets a and set b:`
```console
>>> a = {1, 2, 2, 3, 4}
>>> b = {3, 3, 4, 4, 5}
```
`Intersection`

a.intersection(b) returns a new set with elements present in both a and b
```console
>>> a.intersection(b)
{3, 4}
```
`Union`

a.union(b) returns a new set with elements present in either a and b
```console
>>> a.union(b)
{1, 2, 3, 4, 5}
```
`Difference`

a.difference(b) returns a new set with elements present in a but not in b
```console
>>> a.difference(b)
{1, 2}
>>> b.difference(a)
{5}
```
`Symmetric Difference`

a.symmetric_difference(b) returns a new set with elements present in either a or b but not in both
```console
>>> a.symmetric_difference(b)
{1, 2, 5}
>>> b.symmetric_difference(a)
{1, 2, 5}
```
> NOTE: a.symmetric_difference(b) == b.symmetric_difference(a)

`Subset and superset`
- c.issubset(a) tests whether each element of c is in a.
- a.issuperset(c) tests whether each element of c is in a.
```console
>>> c = {1, 2}
>>> c.issubset(a)
True
>>> a.issuperset(c)
True
```
> The latter operations have equivalent operators as shown below:

|Method |Operator|
|:---|:---|
|a.intersection(b) | a & b|
|a.union(b) | a \| b|
|a.difference(b) | a - b|
|a.symmetric_difference(b) | a ^ b|
|a.issubset(b) | a <= b|
|a.issuperset(b) | a >= b|

`Disjoint sets` - Sets a and d are disjoint if no element in a is also in d and vice versa.
```console
>>> d = {5, 6}
>>> a.isdisjoint(b) # {2, 3, 4} are in both sets
False
>>> a.isdisjoint(d)
True
# This is an equivalent check, but less efficient
>>> len(a & d) == 0
True
# This is even less efficient
>>> a & d == set()
True
```
`Length` -
The builtin `len()` function returns the number of elements in the set
```console
>>> len(a)
4
>>> len(b)
3
```

1.4. Dictionary
---

### 1.4.1. Introduction
- A dictionary is an example of a key value store also known as Mapping in Python
-  It allows you to store and retrieve elements by referencing a key. 
-  As dictionaries are referenced by key, they have very fast lookups. 
-  As they are primarily used for referencing items by key
-  They are not sorted.
### 1.4.2. Creating a dictionary
**Rules for creating a dictionary:**
- Every key must be **unique** (otherwise it will be overridden)
- Every key must be **hashable** (can use the hash function to hash it; otherwise TypeError will be thrown)
- There is no particular order for the keys.
```python
# Creating and populating it with values
stock = {'eggs': 5, 'milk': 2}

# Or creating an empty dictionary
dictionary = {}

# And populating it after
dictionary['eggs'] = 5
dictionary['milk'] = 2
```
```python
# Values can also be lists
mydict = {'a': [1, 2, 3], 'b': ['one', 'two', 'three']}

# Use list.append() method to add new elements to the values list
mydict['a'].append(4) # => {'a': [1, 2, 3, 4], 'b': ['one', 'two', 'three']}
mydict['b'].append('four') # => {'a': [1, 2, 3, 4], 'b': ['one', 'two', 'three', 'four']}
```
```python
# We can also create a dictionary using a list of two-items tuples
iterable = [('eggs', 5), ('milk', 2)]
dictionary = dict(iterable)

# Or using keyword argument:
dictionary = dict(eggs=5, milk=2)

# Another way will be to use the dict.fromkeys:
dictionary = dict.fromkeys((milk, eggs)) # => {'milk': None, 'eggs': None}
dictionary = dict.fromkeys((milk, eggs), (2, 5)) # => {'milk': 2, 'eggs': 5}
```
### 1.4.3. Avoiding KeyError Exceptions
- One common pitfall when using dictionaries is to access a non-existent key. 
- This typically results in a KeyError
exception
```python
mydict = {}
mydict['not there']

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'not there'
```
One way to avoid `key errors` is to use the dict.get method, which allows you to specify a default value to return in
the case of an absent key.
```python
value = mydict.get(key, default_value)
```
- Which returns `mydict[key]` if it exists, but otherwise returns default_value. 
> Note that this doesn't add key to mydict. 
- So if you want to retain that key value pair, you should use `mydict.setdefault(key, default_value)`, which does store the key value pair.
```python
mydict = {}
print(mydict)
# {}
print(mydict.get("foo", "bar"))
# bar
print(mydict)
# {}
print(mydict.setdefault("foo", "bar"))
# bar
print(mydict)
# {'foo': 'bar'}
```
An alternative way to deal with the problem is catching the exception
```python
try:
  value = mydict[key]
except KeyError:
  value = default_value
```
You could also check if the key is in the dictionary
```python
if key in mydict:
  value = mydict[key]
else:
  value = default_value
```

### 1.4.4. Iterating Over a Dictionary
> The methods `keys()`, `values()` and `items()` return lists

`for loop`
```python
d = {'a': 1, 'b': 2, 'c':3}
for key in d:
 print(key, d[key])
# c 3
# b 2
# a 1
```
The same is true when used in a comprehension
```python
print([key for key in d])
# ['c', 'b', 'a']
```
The items() method can be used to loop over both the key and value simultaneously:
```python
for key, value in d.items():
  print(key, value)
# c 3
# b 2
# a 1
```
While the values() method can be used to iterate over only the values, as would be expected:
```python
for key, value in d.values():
  print(key, value)
# 3
# 2
# 1
```

### 1.4.5. Accessing keys and values
```python
mydict = {'a': '1', 'b': '2'}
```
`keys()` - Get a list of keys:
```python
print(mydict.keys())
# Python2: ['a', 'b']
# Python3: dict_keys(['b', 'a'])
```
`values()` - Get a list of values:
```python
print(mydict.values())
# Python2: ['1', '2']
# Python3: dict_values(['2', '1'])
```
`items()` - Get a list of tuple both the key and its corresponding value:
```python
print(mydict.items())
# Python2: [('a', '1'), ('b', '2')]
# Python3: dict_items([('b', '2'), ('a', '1')])
```
> NOTE: Because a dict is unsorted, `keys()`, `values()`, and `items()` have no sort order. Use `sort()`, `sorted()`, or an `OrderedDict` if you care about the order that these methods return.
### 1.4.6. The trailing comma
Like lists and tuples, you can include a trailing comma in your dictionary.
```python
role = {"By day": "A typical programmer",
        "By night": "Still a typical programmer", }
```

### 1.4.7. The dict() constructor
The `dict()` constructor can be used to create dictionaries from keyword arguments, or from a single iterable of key-value pairs, or from a single dictionary and keyword arguments.
```python
dict(a=1, b=2, c=3) # {'a': 1, 'b': 2, 'c': 3}
dict([('d', 4), ('e', 5), ('f', 6)]) # {'d': 4, 'e': 5, 'f': 6}
dict([('a', 1)], b=2, c=3) # {'a': 1, 'b': 2, 'c': 3}
dict({'a' : 1, 'b' : 2}, c=3) # {'a': 1, 'b': 2, 'c': 3}
```
1.5. Tuple
---
### 1.5.1. Tuple
Syntactically, a tuple is a comma-separated list of values:
```python
t = 'a', 'b', 'c', 'd', 'e'
```
Although not necessary, it is common to enclose tuples in parentheses:
```python
t = ('a', 'b', 'c', 'd', 'e')
```
Create an empty tuple with parentheses:
```python
t0 = ()
type(t0) # <type 'tuple'>
```
To create a tuple with a single element, you have to include a final comma:
```python
t1 = 'a',
type(t1) # <type 'tuple'>
```
Note that a single value in parentheses is not a tuple:
```python
t2 = ('a')
type(t2) # <type 'str'>
```
To create a singleton tuple it is necessary to have a trailing comma.
```python
t2 = ('a',)
type(t2) # <type 'tuple'>
```
Another way to create a tuple is the built-in function tuple.
```python
t = tuple('lupins')
print(t) # ('l', 'u', 'p', 'i', 'n', 's')
t = tuple(range(3))
print(t) # (0, 1, 2)
```
### 1.5.2. Tuples are immutable
- One of the main differences between lists and tuples in Python is that tuples are `immutable`
- That is, one cannot add or modify items once the tuple is initialized.
```console
>>> t = (1, 4, 9)
>>> t[0] = 2
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```
- Similarly, tuples don't have `.append` and `.extend `methods as list does. Using `+=` is possible
- But it changes the binding of the variable, and not the tuple itself:
```console
>>> t = (1, 2)
>>> q = t
>>> t += (3, 4)
>>> t
(1, 2, 3, 4)
>>> q
(1, 2)
```
Be careful when placing mutable objects, such as lists, inside tuples. This may lead to very confusing outcomes when changing them.
```console
>>> t = (1, 2, 3, [1, 2, 3])
(1, 2, 3, [1, 2, 3])
>>> t[3] += [4, 5]
```
Will both raise an error and change the contents of the list within the tuple:
```console
TypeError: 'tuple' object does not support item assignment
>>> t
(1, 2, 3, [1, 2, 3, 4, 5])
```

###  1.5.3. Built-in Tuple Functions
- Comparision
- Tuple Length
- Max of a Tuple
- Min of a Tuple
- Convert a list into tuple
- Tuple concatenation

`Comparision`

If elements are of the same type, python performs the comparison and returns the result. 
If elements are different types, it checks whether they are numbers.
- If numbers, perform comparison.
- If either element is a number, then the other element is returned.
- Otherwise, types are sorted alphabetically.

If we reached the end of one of the lists, the longer list is "larger." If both list are same it returns 0.
```python
tuple1 = ('a', 'b', 'c', 'd', 'e')
tuple2 = ('1','2','3')
tuple3 = ('a', 'b', 'c', 'd', 'e')

cmp(tuple1, tuple2) #Out: 1
cmp(tuple2, tuple1) #Out: -1
cmp(tuple1, tuple3) #Out: 0
```
`Tuple Length`

The function len returns the total length of the tuple
```python
len(tuple1) #Out: 5
```
`Max of a tuple`

The function max returns item from the tuple with the max value
```python
max(tuple1) #Out: 'e'
max(tuple2) #Out: '3'
```
`Min of a tuple`

The function min returns the item from the tuple with the min value
```python
min(tuple1) #Out: 'a'
min(tuple2) #Out: '1'
```
`Convert a list into tuple`

The built-in function tuple converts a list into a tuple.
```python
list = [1,2,3,4,5]
tuple(list)       #Out: (1, 2, 3, 4, 5)
```
`Tuple concatenation`

Use + to concatenate two tuples
```python
tuple1 + tuple2     #Out: ('a', 'b', 'c', 'd', 'e', '1', '2', '3')
```

### 1.5.4. Indexing Tuples
```python
x = (1, 2, 3)
x[0] # 1
x[1] # 2
x[2] # 3
x[3] # IndexError: tuple index out of range
```
Indexing with negative numbers will start from the last element as -1:
```python
x[-1] # 3
x[-2] # 2
x[-3] # 1
x[-4] # IndexError: tuple index out of range
```
Indexing a range of elements
```python
print(x[:-1]) # (1, 2)
print(x[-1:]) # (3,)
print(x[1:3]) # (2, 3)
```
###  1.5.5. Reversing Elements
```python
Reverse elements within a tuple
colors = "red", "green", "blue"
rev = colors[::-1]
# rev: ("blue", "green", "red")
colors = rev
# colors: ("blue", "green", "red")
```
Or using reversed (reversed gives an iterable which is converted to a tuple):
```python
rev = tuple(reversed(colors))
# rev: ("blue", "green", "red")
colors = rev
# colors: ("blue", "green", "red")
```
