# Loops


**Loops:**
- [Loops](#loops)
  - [For Loop](#for-loop)
  - [While Loop](#while-loop)
  - [Loops with an "else" clause](#loops-with-an-else-clause)
  - [Break](#break)
  - [Continue](#continue)
  - [Pass](#pass)


For Loop
---
`for Loop` loops iterate over a collection of items, such as `list` or `dict`, and run a block of code with each element from the collection.
```python
for i in [0, 1, 2, 3, 4]:
 print(i)
```
- The above `for` loop iterates over a list of numbers.  

- Each iteration sets the value of i to the next element of the list. So first it will be 0, then 1, then 2, etc.    

The output will be as follow:
```
0
1
2
3
4
```
`range` is a function that returns a series of numbers under an iterable form, thus it can be used in `for` loops:
```python
for i in range(5):
 print(i)
```
gives the exact same result as the first `for` loop. Note that 5 is not printed as the range here is the first five numbers counting from 0.

While Loop
---
- A `while` loop will cause the loop statements to be executed until the loop condition is falsey.
- The following code will execute the loop statements a total of 4 times.
```
i = 0
while i < 4:
 #loop statements
 i = i + 1
```
- While the above loop can easily be translated into a more elegant `for` loop, `while` loops are useful for checking if some condition has been met. 
- The following loop will continue to execute until myObject is ready.
```python
myObject = anObject()
while myObject.isNotReady():
    myObject.tryToGetReady()
```
`while` loops can also run without a condition by using numbers (complex or real) or `True`:
```python
import cmath
complex_num = cmath.sqrt(-1)
while complex_num: # You can also replace complex_num with any number, True or a value of any type
    print(complex_num) # Prints 1j forever
```
- If the condition is always true the while loop will run forever (infinite loop) 
- if it is not terminated by a break or return
statement or an exception.
```python
while True:
    print "Infinite loop"
# Infinite loop
# Infinite loop
# Infinite loop
# ..
```

Loops with an "else" clause
---
> The `else` clause only executes after a `for` loop terminates by iterating to completion, or after a `while` loop terminates by its conditional expression becoming false.
```python
for i in range(3):
    print(i)
else:
    print('done')
```
```python
i = 0
while i < 3:
    print(i)
    i += 1
else:
    print('done')
```
Output:
```
0
1
2
done
```
The `else` clause does not execute if the loop terminates some other way (through a `break` statement or by raising an exception):
```python
for i in range(2):
    print(i)
    if i == 1:
        break
else:
    print('done')
```
Output:
```
0
1
```

Break
---
When a `break` statement executes inside a loop, control flow "breaks" out of the loop immediately:
```python
i = 0
while i < 7:
    print(i)
    if i == 4:
        print("Breaking from loop")
        break
    i += 1
```
- The loop conditional will not be evaluated after the `break` statement is executed.   
- Note that `break` statements are only allowed inside loops, syntactically.   
- A `break` statement inside a function cannot be used to terminate loops that called that function.   
> Executing the following prints every digit until number 4 when the break statement is met and the loop stops:
```
0
1
2
3
4
Breaking from loop
```
`break` statements can also be used inside for loops, the other looping construct provided by Python:
```python
for i in (0, 1, 2, 3, 4):
    print(i)
    if i == 2:
        break
```
Executing this loop now prints:
```
0
1
2
```
> Note that 3 and 4 are not printed since the loop has ended.

> If a loop has an `else` clause, it does not execute when the loop is terminated through a `break` statement.

Continue
---
- A `continue` statement will skip to the next iteration of the loop bypassing the rest of the current block but continuing the loop. 
- As with `break`, `continue` can only appear inside loops:
```python
for i in (0, 1, 2, 3, 4, 5):
    if i == 2 or i == 4:
        continue
    print(i)

0
1
3
5
```
> Note that 2 and 4 aren't printed, this is because `continue` goes to the next iteration instead of continuing on to **print(i) when i == 2 or i == 4.**

Pass
---
- `pass` is a null statement for when a statement is required by Python syntax, but no action is required or desired by the programmer. 
- **This can be useful as a placeholder for code that is yet to be written.**
```python
for x in range(10):
 pass #we don't want to do anything, or are not ready to do anything here, so we'll pass
```
- In this example, nothing will happen. The `for` loop will complete without error, but no commands or code will be actioned. `pass` allows us to run our code successfully without having all commands and action fully implemented.
- Similarly, `pass` can be used in `while` loops, as well as in selections and function definitions etc.
```python
while x == y:
 pass
```
