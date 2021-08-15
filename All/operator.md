# Operators

**Operators:**
- [Operators](#operators)
  - [Simple Mathematical Operator](#simple-mathematical-operator)
    - [`Division`](#division)
    - [`Modulus`](#modulus)
    - [`Multiplication`](#multiplication)
    - [`Addition`](#addition)
    - [`Subtraction`](#subtraction)
    - [`Exponentiation`](#exponentiation)
    - [`Trigonometric Functions`](#trigonometric-functions)
    - [`Inplace Operations`](#inplace-operations)
    - [`Logarithms`](#logarithms)
  - [Bitwise Operator](#bitwise-operator)
    - [`Bitwise NOT`](#bitwise-not)
    - [`Bitwise XOR (Exclusive OR)`](#bitwise-xor-exclusive-or)
    - [`Bitwise AND`](#bitwise-and)
    - [`Bitwise OR`](#bitwise-or)
    - [`Bitwise Left Shift`](#bitwise-left-shift)
    - [`Bitwise Right Shift`](#bitwise-right-shift)
    - [`Inplace Operations`](#inplace-operations-1)
  - [Boolean Operator](#boolean-operator)
    - [`and`](#and)
    - [`or`](#or)
    - [`not`](#not)
  - [Operator Precedence](#operator-precedence)
  - [Comparisions](#comparisions)
    - [`Comparison by 'is' vs '=='`](#comparison-by-is-vs-)
    - [` Greater than or less than`](#-greater-than-or-less-than)
    - [`Not equal to`](#not-equal-to)
    - [`Equal to`](#equal-to)


Simple Mathematical Operator
---
### `Division`
```python
a, b, c, d, e = 3, 2, 2.0, -3, 10
```
`Python 2.x`    Version ≤ 2.7   
In Python 2 the result of the ' / ' operator depends on the type of the numerator and denominator.
```python
a / b       # = 1
a / c       # = 1.5
d / b       # = -2
b / a       # = 0
d / e       # = -1
```
> - Note that because both a and b are ints, the result is an int.
> - The result is always rounded down (floored).
> - Because c is a float, the result of a / c is a float.

`Python 3.x` Version ≥ 3.0   
In Python 3 the / operator performs 'true' division regardless of types. The // operator performs floor division and
maintains type.
```python
a / b # = 1.5
e / b # = 5.0
a // b # = 1
a // c # = 1.0
```
```python
import operator # the operator module provides 2-argument arithmetic functions
operator.truediv(a, b) # = 1.5
operator.floordiv(a, b) # = 1
operator.floordiv(a, c) # = 1.0
```
**Possible combinations (builtin types):**   
- `int` and `int` (gives an `int` in Python 2 and a `float` in Python 3)
- `int` and `float` (gives a `float`)
- `int` and `complex` (gives a `complex`)
- `float` and `float` (gives a `float`)
- `float` and `complex` (gives a `complex`)
- `complex` and `complex` (gives a `complex`)

### `Modulus`
Like in many other languages, Python uses the % operator for calculating modulus.
```python
3 % 4 # 3
10 % 2 # 0
6 % 4 # 2
```
Or by using the operator module:
```python
import operator
operator.mod(3 , 4) # 3
operator.mod(10 , 2) # 0
operator.mod(6 , 4) # 2
```
You can also use negative numbers.
```python
-9 % 7 # 5
9 % -7 # -5
-9 % -7 # -2
```
If you need to find the result of integer division and modulus, you can use the divmod function as a shortcut:
```python
quotient, remainder = divmod(9, 4)
# quotient = 2, remainder = 1 as 4 * 2 + 1 == 9
```
### `Multiplication`
```python
a, b = 2, 3

a * b               # 6

import operator
operator.mul(a, b)  # 6
```
Possible combinations (builtin types):
- `int` and `int` (gives an `int`)
- `int` and `float` (gives a `float`)
- `int` and `complex` (gives a `complex`)
- `float` and `float` (gives a `float`)
- `float` and `complex` (gives a `complex`)
- `complex` and `complex` (gives a `complex`)
> Note: The * operator is also used for repeated concatenation of strings, lists, and tuples:
```pyhton
3 * 'ab'        #  'ababab'
3 * ('a', 'b')  #  ('a', 'b', 'a', 'b', 'a', 'b')
```

### `Addition`   
```python
a, b = 1, 2

# Using the "+" operator:
a + b # = 3

# Using the "in-place" "+=" operator to add and assign:
a += b # a = 3 (equivalent to a = a + b)
```
```python
import operator # contains 2 argument arithmetic functions for the examples
operator.add(a, b) # = 5 since a is set to 3 right before this line

# The "+=" operator is equivalent to:
a = operator.iadd(a, b) # a = 5 since a is set to 3 right before this line
```
**Possible combinations (builtin types):**
- `int` and `int` (gives an `int`)
- `int` and `float` (gives a `float`)
- `int` and `complex` (gives a `complex`)
- `float` and `float` (gives a `float`)
- `float` and `complex` (gives a `complex`)
- `complex` and `complex` (gives a `complex`)
> Note: the + operator is also used for concatenating strings, lists and tuples:
```python
"first string " + "second string" # = 'first string second string'

[1, 2, 3] + [4, 5, 6]   # [1, 2, 3, 4, 5, 6]
```
### `Subtraction`
```python
a, b = 1, 2

# Using the "-" operator:
b - a # = 1

import operator # contains 2 argument arithmetic functions
operator.sub(b, a) # = 1
```
Possible combinations (builtin types):
- `int` and `int` (gives an `int`)
- `int` and `float` (gives a `float`)
- `int` and `complex` (gives a `complex`)
- `float` and `float` (gives a `float`)
- `float` and `complex` (gives a `complex`)
- `complex` and `complex` (gives a `complex`)

### `Exponentiation`
```python
a, b = 2, 3

(a ** b)    # = 8
pow(a, b)   # = 8
```
```python
import math
math.pow(a, b) # = 8.0 (always float; does not allow complex results)
```
```python
import operator
operator.pow(a, b)  # 8
```
> Another difference between the built-in pow and math.pow is that the built-in pow can accept three arguments:
```python
a, b, c = 2, 3, 2
pow(2, 3, 2)    # 0, calculates (2 ** 3) % 2, but as per Python docs,
                # does so more efficiently
```
```python
import math
x = 8
math.pow(x, 1/3) # evaluates to 2.0
x**(1/3) # evaluates to 2.0
```
The function `math.exp(x)` computes `e ** x`
```python
math.exp(0) # 1.0
math.exp(1) # 2.718281828459045 (e)
```
The function `math.expm1(x)` computes `e ** x - 1`.  
When x is small, this gives significantly better precision than `math.exp(x) - 1`.
```python
math.expm1(0) # 0.0
math.exp(1e-6) - 1 # 1.0000004999621837e-06
math.expm1(1e-6) # 1.0000005000001665e-06
# exact result # 1.000000500000166666708333341666...
```

### `Trigonometric Functions`
```python
a, b = 1, 2

import math
math.sin(a) # returns the sine of 'a' in radians
# Out: 0.8414709848078965

math.cosh(b) # returns the inverse hyperbolic cosine of 'b' in radians
# Out: 3.7621956910836314

math.atan(math.pi) # returns the arc tangent of 'pi' in radians
# Out: 1.2626272556789115

math.hypot(a, b) # returns the Euclidean norm, same as math.sqrt(a*a + b*b)
# Out: 2.23606797749979
```
To convert from radians -> degrees and degrees -> radians respectively use `math.degrees` and `math.radians`
```python
math.degrees(a) # Out: 57.29577951308232

math.radians(57.29577951308232) # Out: 1.0
```
### `Inplace Operations`   
It is common within applications to need to have code like this:
```python
a = a + 1
or
a = a * 2
```
There is an effective shortcut for these in place operations:
```python
a += 1
or
a *= 2
```
Any mathematic operator can be used before the '=' character to make an inplace operation:
- `-=` decrement the variable in place
- `+=` increment the variable in place
- `*=` multiply the variable in place
- `/=` divide the variable in place
- `//=` floor divide the variable in place # Python 3
- `%=` return the modulus of the variable in place
- `**=` raise to a power in place

### `Logarithms`   
By default, the `math.log` function calculates the logarithm of a number, base e. You can optionally specify a base as the second argument.
```python
import math
import cmath

math.log(5)             # = 1.6094379124341003
# optional base argument. Default is math.e
math.log(5, math.e)     # = 1.6094379124341003
cmath.log(5)            # = (1.6094379124341003+0j)
math.log(1000, 10)      # 3.0 (always returns float)
cmath.log(1000, 10)     # (3+0j)
```
Special variations of the `math.log` function exist for different bases.
```python
# Logarithm base e - 1 (higher precision for low values)
math.log1p(5)           # = 1.791759469228055

# Logarithm base 2
math.log2(8)            # = 3.0

# Logarithm base 10
math.log10(100)         # = 2.0
cmath.log10(100)        # = (2+0j)
```

Bitwise Operator
---
- Bitwise operations alter binary strings at the bit level. 
- These operations are incredibly basic and are directly
supported by the processor.
### `Bitwise NOT`
The `~` operator will flip all of the bits in the number   
Since computers use `signed number representations`    
    — most notably, the `two's complement` notation to encode negative binary numbers where negative numbers are written with a leading one (1) instead of a leading zero (0).
|Bits |Unsigned Value| Two's-complement Value|
|:---:|:---:|:---:|
|0000 0000 |0 |0|
|0000 0001 |1 |1|
|0000 0010 2 |2|
|0111 1110 |126 |126|
|0111 1111 |127| 127|
|1000 0000 |128| -128|
|1000 0001 |129| -127|
|1000 0010 |130| -126|
|1111 1110 |254| -2|
|1111 1111 |255| -1|

```python
# 0 = 0b0000 0000
~0
# Out: -1
# -1 = 0b1111 1111

# 1 = 0b0000 0001
~1
# Out: -2
# -2 = 1111 1110

# 123 = 0b0111 1011
~123
# Out: -124
# -124 = 0b1000 0100
```
### `Bitwise XOR (Exclusive OR)`
The `^` operator will perform a binary `XOR` in which a binary 1 is copied if and only if it is the value of exactly one operand.   
Another way of stating this is that the result is 1 only if the operands are different. 

|XOR|Result|
|:---:|:---:|
|0 ^ 0 | 0|
|0 ^ 1 | 1|
|1 ^ 0 | 1|
|1 ^ 1 | 0|
```python
# 60 = 0b111100
# 30 = 0b011110
60 ^ 30
# Out: 34
# 34 = 0b100010

bin(60 ^ 30)
# Out: 0b100010
```
### `Bitwise AND`
The `&` operator will perform a binary `AND`, where a bit is copied if it exists in `both` operands. 

|AND|Result|
|:---:|:---:|
|0 & 0 | 0|
|0 & 1 | 0|
|1 & 0 | 0|
|1 & 1 | 1|
```python
# 60 = 0b111100
# 30 = 0b011110
60 & 30
# Out: 28
# 28 = 0b11100

bin(60 & 30)
# Out: 0b11100
```
### `Bitwise OR`
The `|` operator will perform a binary `or`, where a bit is copied if it exists in either operand. 

|OR|Result|
|:---:|:---:|
|0 \| 0 | 0|
|0 \| 1 | 1|
|1 \| 0 | 1|
|1 \| 1 | 1|
```python
# 60 = 0b111100
# 30 = 0b011110
60 | 30
# Out: 62
# 62 = 0b111110

bin(60 | 30)
# Out: 0b111110
```
### `Bitwise Left Shift`
The `<<` operator will perform a bitwise `left shift`, where the left operand's value is moved left by the number of bits given by the right operand.
```python
# 2 = 0b10
2 << 2
# Out: 8
# 8 = 0b1000

bin(2 << 2)
# Out: 0b1000
```
Performing a left bit shift of 1 is equivalent to multiplication by 2:
```python
7 << 1
# Out: 14
```
Performing a left bit shift of n is equivalent to multiplication by 2**n:

```python
3 << 4
# Out: 48
```
### `Bitwise Right Shift`
The `>>` operator will perform a bitwise `right shift`, where the left operand's value is moved right by the number of
bits given by the right operand.
```python
# 8 = 0b1000
8 >> 2
# Out: 2
# 2 = 0b10
bin(8 >> 2)
# Out: 0b10
```
Performing a right bit shift of 1 is equivalent to integer division by 2:
```python
36 >> 1
# Out: 18
15 >> 1
# Out: 7
```
Performing a right bit shift of n is equivalent to integer division by 2**n:
```python
48 >> 4
# Out: 3
59 >> 3
# Out: 7
```

### `Inplace Operations`
All of the Bitwise operators (except ~) have their own in place versions
```python
a = 0b001
a &= 0b010
# a = 0b000

a = 0b001
a |= 0b010
# a = 0b011

a = 0b001
a <<= 2
# a = 0b100

a = 0b100
a >>= 2
# a = 0b001

a = 0b101
a ^= 0b011
# a = 0b110
```

Boolean Operator
---
### `and`
Evaluates to the second argument if and only if both of the arguments are truthy. Otherwise evaluates to the first falsey argument.
```python
x = True
y = True
z = x and y # z = True

x = True
y = False
z = x and y # z = False

x = False
y = True
z = x and y # z = False

x = False
y = False
z = x and y # z = False
```
```python
x = 1
y = 1
z = x and y # z = y, so z = 1, see `and` and `or` are not guaranteed to be a boolean

x = 0
y = 1
z = x and y # z = x, so z = 0 (see above)

x = 1
y = 0
z = x and y # z = y, so z = 0 (see above)

x = 0
y = 0
z = x and y # z = x, so z = 0 (see above)
```
The 1's in the above example can be changed to any truthy value, and the 0's can be changed to any falsey value.
### `or`
Evaluates to the first truthy argument if either one of the arguments is truthy. If both arguments are falsey, evaluates to the second argument.
```python
x = True
y = True
z = x or y # z = True

x = True
y = False
z = x or y # z = True

x = False
y = True
z = x or y # z = True

x = False
y = False
z = x or y # z = False
```
```python
x = 1
y = 1
z = x or y # z = x, so z = 1, see `and` and `or` are not guaranteed to be a boolean

x = 1
y = 0
z = x or y # z = x, so z = 1 (see above)

x = 0
y = 1
z = x or y # z = y, so z = 1 (see above)

x = 0
y = 0
z = x or y # z = y, so z = 0 (see above)
```
The 1's in the above example can be changed to any truthy value, and the 0's can be changed to any falsey value.

### `not`
It returns the opposite of the following statement:
```python
x = True
y = not x # y = False

x = False
y = not x # y = True
```
Operator Precedence
---
Python follows PEMDAS rule. 
PEMDAS
- `Parentheses`
- `Exponents`
- `Multiplication`
- `Division`
- `Addition`
- `Subtraction`.
```console
>>> a, b, c, d = 2, 3, 5, 7
>>> a ** (b + c) # parentheses
256

>>> a * b ** c # exponent: same as `a * (b ** c)`
7776

>>> a + b * c / d # multiplication / division: same as `a + (b * c / d)`
4.142857142857142
```
Comparisions
---
### `Comparison by 'is' vs '=='`
A common pitfall is confusing the equality comparison operators is and ==.
- `a == b` compares the `value` of a and b.
- `a is b` will compare the `identities` of a and b.
```python
a = 'Python is fun!'
b = 'Python is fun!'
a == b # returns True
a is b # returns False

a = [1, 2, 3, 4, 5]
b = a # b references a
a == b # True
a is b # True
b = a[:] # b now references a copy of a
a == b # True
a is b # False [!!]
```
> Basically, is can be thought of as shorthand for id(a) == id(b).

### ` Greater than or less than`
```
x > y
x < y
```
```python
12 > 4
# True

12 < 4
# False

1 < 4
# True
```
For strings they will compare lexicographically, which is similar to alphabetical order but not quite the same.
```python
"alpha" < "beta"
# True

"gamma" > "beta"
# True

"gamma" < "OMEGA"
# False
```
In these comparisons, lowercase letters are considered 'greater than' uppercase, which is why `"gamma" < "OMEGA"` is false. If they were all uppercase it would return the expected alphabetical ordering result:
```python
"GAMMA" < "OMEGA"
# True
```

### `Not equal to`
```
x != y
```
This returns `True` if x and y are not equal and otherwise returns `False`.

```python
12 != 1
# True

12 != '12'
# True

'12' != '12'
# False
```

### `Equal to`
```
x == y
```
This expression evaluates if x and y are the same value and returns the result as a boolean value.    
Generally both type and value need to match, so the int `12` is not the same as the string `'12'`.

```python
12 == 12
# True

12 == 1
# False

'12' == '12'
# True

'spam' == 'spam'
# True

'spam' == 'spam '
# False

'12' == 12
# False
```