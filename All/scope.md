# Variable Scope

**Variable Scope:**
- [Variable Scope](#variable-scope)
  - [Non Local variables](#non-local-variables)
  - [Local variables](#local-variables)
  - [Global variables](#global-variables)
  - [Examples](#examples)


Non Local variables
---
- Python 3 added a new keyword called `nonlocal.` 
- The `nonlocal` keyword adds a scope override to the inner scope.
```python
def counter():
    num = 0
    def incrementer():
        num += 1
        return num
    return incrementer
```
If you try running this code, you will receive an **UnboundLocalError** because the num variable is referenced before it is assigned in the innermost function. Let's add `nonlocal` to the mix:
```python
def counter():
    num = 0
    def incrementer():
        nonlocal num
        num += 1
        return num
    return incrementer

c = counter()
c() # = 1
c() # = 2
c() # = 3
```
> Basically `nonlocal` will allow you to assign to variables in an outer scope, but not a global scope. So you can't use nonlocal in our counter function because then it would try to assign to a global scope.

Local variables
---
If a name is bound inside a function, it is by default accessible only within the function:
```python
def foo():
    a = 5
    print(a) # ok

print(a) # NameError: name 'a' is not defined
```
Control flow constructs have no impact on the scope (with the exception of except), but accessing variable that was
not assigned yet is an error:
```python
def foo():
    if True:
    a = 5
    print(a) # ok

b = 3
def bar():
    if False:
        b = 5
    print(b) # UnboundLocalError: local variable 'b' referenced before assignment
```
Common binding operations are assignments, for loops, and augmented assignments such as a += 5

Global variables
---
In Python, variables inside functions are considered local if and only if they appear in the left side of an assignment statement, or some other binding occurrence; otherwise such a binding is looked up in enclosing functions, up to the global scope. This is true even if the assignment statement is never executed

```python
x = 'Hi'
def read_x():
    print(x) # x is just referenced, therefore assumed global

read_x() # prints Hi

def read_y():
    print(y) # here y is just referenced, therefore assumed global

read_y() # NameError: global name 'y' is not defined

def read_y():
    y = 'Hey' # y appears in an assignment, therefore it's local
    print(y) # will find the local y

read_y() # prints Hey

def read_x_local_fail():
    if False:
        x = 'Hey' # x appears in an assignment, therefore it's local
    print(x) # will look for the _local_ z, which is not assigned, and will not be found
read_x_local_fail() # UnboundLocalError: local variable 'x' referenced before assignment
```
Normally, an assignment inside a scope will shadow any outer variables of the same name:
```python
x = 'Hi'
def change_local_x():
    x = 'Bye'
    print(x)

change_local_x()    # prints Bye
print(x)            # prints Hi
```
Declaring a name global means that, for the rest of the scope, any assignments to the name will happen at the
module's top level:
```python
x = 'Hi'
def change_global_x():
    global x
    x = 'Bye'
    print(x)

change_global_x() # prints Bye
print(x) # prints Bye
```
The global keyword means that assignments will happen at the module's top level, not at the program's top level. Other modules will still need the usual dotted access to variables within the module.
To summarize: in order to know whether a variable x is local to a function, you should read the entire function:
1. if you've found `global` x, then x is a **global** variable
2. If you've found `nonlocal` x, then x belongs to an enclosing function, and is neither local nor global
3. If you've found `x = 5` or `for x in range(3)` or some other binding, then x is a **local** variable
4. Otherwise x belongs to some enclosing scope (function scope, global scope, or builtins)

Examples
---
```python
foo = 1 # global
def func():
    bar = 2 # local
    print(foo) # prints variable foo from global scope
    print(bar) # prints variable bar from local scope
```
```python
foo = 1
def func():
    foo = 2 # creates a new variable foo in local scope, global foo is not affected

    print(foo) # prints 2

    # global variable foo still exists, unchanged:
    print(globals()['foo']) # prints 1
    print(locals()['foo']) # prints 2
```

