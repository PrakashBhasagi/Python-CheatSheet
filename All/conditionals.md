# Conditionals

**Conditionals:**
- [Conditionals](#conditionals)
  - [Ternary Operator](#ternary-operator)
  - [If Statement](#if-statement)
  - [If Elif and Else](#if-elif-and-else)
  - [Truth Values](#truth-values)


Ternary Operator
---
The ternary operator is used for inline conditional expressions. It is best used in simple, concise operations that are
easily read.
```python
n = 5

"Greater than 2" if n > 2 else "Smaller than or equal to 2"
# Out: 'Greater than 2'
```
The result of this expression will be as it is read in English - if the conditional expression is True, then it will evaluate to the expression on the left side, otherwise, the right side.

Ternary operations can also be nested, as here:
```python
n = 5
"Hello" if n > 10 else "Goodbye" if n > 5 else "Good day"
```
They also provide a method of including conditionals in lambda functions

If Statement
--- 
```python
if condition:
    body
```
The if statements checks the condition. If it evaluates to `True`, it executes the body of the if statement. If it
evaluates to `False`, it skips the body.
```console
if True:
 print "It is true!"
>> It is true!
if False:
 print "This won't get printed.."
```
The condition can be any valid expression:
```console
if 2 + 2 == 4:
 print "I know math!"
>> I know math!
```


If Elif and Else
---
> In Python you can define a series of conditionals using if for the first one, elif for the rest, up until the final (optional) else for anything not caught by the other conditionals.
```python
number = 5
if number > 2:
    print("Number is bigger than 2.")
elif number < 2: # Optional clause (you can have multiple elifs)
    print("Number is smaller than 2.")
else: # Optional clause (you can only have one else)
    print("Number is 2.")
```
> Outputs Number is `bigger than` 2   
> Using `else if` instead of `elif` will trigger a syntax error and is not allowed.

Truth Values
---
The following values are considered falsey, in that they evaluate to False when applied to a boolean operator.
- None
- False
- 0, or any numerical value equivalent to zero, for example 0L, 0.0, 0j
- Empty sequences: '', "", (), []
- Empty mappings: {}
- User-defined types where the `__bool__` or `__len__` methods return 0 or False

All other values in Python evaluate to `True`.
