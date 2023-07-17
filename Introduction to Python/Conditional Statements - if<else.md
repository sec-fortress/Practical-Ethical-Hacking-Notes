In Python, conditional statements are used to perform different actions based on certain conditions. They allow you to control the flow of your program by executing specific blocks of code when certain conditions are met. Here's an explanation of conditional statements in Python:

1. if Statement:
2. The `if` statement is the most basic conditional statement. It executes a block of code if a given condition is true. Here's the general syntax:
```python
if condition:
    # code to be executed if the condition is true
```
Example:

```python
x = 5
if x > 0:
    print("x is positive")
 ```

In this example, the code inside the `if` block (`print("x is positive")`) will be executed if the condition `x > 0` is true.

1. if-else Statement:
2. The `if-else` statement allows you to specify two different blocks of code—one to be executed if the condition is true and another to be executed if the condition is false. Here's the syntax:
```python
if condition:
    # code to be executed if the condition is true
else:
    # code to be executed if the condition is false
```

Example:
```python
x = 5
if x > 0:
    print("x is positive")
else:
    print("x is not positive")
```

In this example, if `x` is greater than 0, the first block (`print("x is positive")`) will be executed. Otherwise, the second block (`print("x is not positive")`) will be executed.

1. if-elif-else Statement:
2. The `if-elif-else` statement allows you to check multiple conditions and execute different blocks of code based on those conditions. It provides more than two options for branching. Here's the syntax:
```python
if condition1:
    # code to be executed if condition1 is true
elif condition2:
    # code to be executed if condition1 is false and condition2 is true
else:
    # code to be executed if all conditions are false
```

Example:
```python
x = 5
if x > 0:
    print("x is positive")
elif x < 0:
    print("x is negative")
else:
    print("x is zero")
```

In this example, if `x` is greater than 0, the first block will be executed. If it is less than 0, the second block will be executed. Otherwise, if none of the conditions are true, the third block will be executed.

Conditional statements allow you to make decisions and control the execution flow of your program based on certain conditions. They are essential for implementing logic and branching in your code.

Here is how it was used in the tutorial:
```python
#Conditional Statements
def drink(money):
	if money >= 2:
		return "You've got yourself a drink!"
	else:
		return "No drink for you!"

print(drink(3))
print(drink(1))


def alcohol(age,money):
	if(age >= 21) and (money >= 5):
		return "We're getting a drink!"
	elif (age >= 21) and (money < 5):
		return "Come back with more money."
	elif (age < 21) and (money >= 5):
		return "Nice try, kid!"
	else:
		return "You're too poor and too young!"
		
print(alcohol(21,5))
print(alcohol(21,4))
print(alcohol(20,5))
print(alcohol(20,4))
```