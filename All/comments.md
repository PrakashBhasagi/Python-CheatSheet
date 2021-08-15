# Comments and Documentation

**Comments and Documentation**
- [Comments and Documentation](#comments-and-documentation)
  - [Single Line Comment](#single-line-comment)
  - [Inline Comment](#inline-comment)
  - [Multiline Comment](#multiline-comment)
  - [Docstrings](#docstrings)
  - [Write documentation using docstrings](#write-documentation-using-docstrings)


> - Comments are used to explain code when the basic code itself
> -  Python ignores comments, and so will not execute code in there, or raise syntax errors for plain English sentences.


Single Line Comment
---
- Begin with the hash character (`#`) and are terminated by the end of line.

```python
# This is a single line comment in Python
```

Inline Comment
---
- Similar to single line comment
```python
print("Hello World") # This line prints "Hello World"
```

Multiline Comment
---
- Comments spanning multiple lines have `"""` or `'''` on either end. This is the same as a multiline string, but
they can be used as comments:

```python
"""
This type of comment spans multiple lines.
These are mostly used for documentation of functions, classes and modules.
"""
```

Docstrings
---
- Docstrings are - unlike regular comments - stored as an attribute of the function they document, meaning that you can access them programmatically.

An example function:
```python
def func():
    """This is a function that does nothing at all"""
    return
```
The docstring can be accessed using the `__doc__ ` attribute:
```python
print(func.__doc__)
```
This is a function that does nothing at all
```python
help(func)
```
> Help on function func in module __main__:   
> 
> func()   
> This is a function that does nothing at all
    
**Another example function**

function.`__doc__` is just the actual docstring as a string, while the `help` function provides general information about a function, including the docstring. Here's a more helpful example:
```python
def greet(name, greeting="Hello"):
    """Print a greeting to the user `name`
    Optional parameter `greeting` can change what they're greeted with."""

    print("{} {}".format(greeting, name))
help(greet)
```
> Help on function greet in module __main__:   
> 
> greet(name, greeting='Hello')
> 
>       Print a greeting to the user name   
>       Optional parameter greeting can change what they're greeted with.

**Advantages of docstrings over regular comments**   
Just putting no docstring or a regular comment in a function makes it a lot less helpful.
```python
def greet(name, greeting="Hello"):
    # Print a greeting to the user `name`
    # Optional parameter `greeting` can change what they're greeted with.

    print("{} {}".format(greeting, name))

print(greet.__doc__)
``` 
> None

```python
help(greet)
```
> Help on function greet in module main:   
  greet(name, greeting='Hello')   

Write documentation using docstrings
---

- A `docstring` is a multi-line comment used to document modules, classes, functions and methods.    
- It has to be the first statement of the component it describes.
```python
def hello(name):
    """Greet someone.
        Print a greeting ("Hello") for the person with the given name.
    """
    print("Hello "+name)

class Greeter:
    """An object used to greet people.
    It contains multiple greeting functions for several languages
    and times of the day.
    """
```
The value of the docstring can be accessed within the program and is - for example - used by the help command.
**Syntax conventions**   
**PEP 257**   
`PEP 257` defines a syntax standard for docstring comments. It basically allows two types:
- One-line Docstrings:

According to PEP 257, they should be used with short and simple functions. Everything is placed in one line,
```python
def hello():
    """Say hello to your friends."""
    print("Hello my friends!")
```
The docstring shall end with a period, the verb should be in the imperative form.   
- Multi-line Docstrings:
  
Multi-line docstring should be used for longer, more complex functions, modules or classes.
```python
def hello(name, language="en"):
    """Say hello to a person.
    Arguments:
    name: the name of the person
    language: the language in which the person should be greeted
    """
    print(greeting[language]+" "+name)
```
