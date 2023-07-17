In Python, variables and methods are fundamental concepts used in programming. Here's an explanation of each:

Variables:

A variable is a named storage location used to store data or values in a program. It acts as a placeholder for data that can be accessed, modified, or used in calculations throughout the program. Variables in Python are dynamically typed, meaning their data type can change during program execution. Here's an example of variable usage in Python:

```python
# Variable assignment
x = 10
name = "John"
is_true = True


# Variable usage
y = x + 5
print("Hello, " + name)
if is_true:
    print("The condition is true")
```

In the example above, `x`, `name`, and `is_true` are variables assigned with different data types (integer, string, and boolean, respectively). They are used in calculations and print statements to perform operations and display values.

Methods:

A method is a block of reusable code that performs a specific task or action. Methods are associated with objects or classes and are called upon to perform certain operations. In Python, methods are commonly referred to as functions. Built-in functions and user-defined functions both fall under the category of methods. Here's an example:

```python
# Built-in method example
numbers = [1, 2, 3, 4, 5]
length = len(numbers)
print("Length:", length)


# User-defined method example
def greet(name):
    print("Hello, " + name)


greet("Alice")
```
In the example above, `len()` is a built-in method that calculates the length of a list (`numbers` in this case). The user-defined method `greet()` takes a parameter `name` and prints a greeting message. It is called with the argument "Alice" to print "Hello, Alice" to the console.

Methods can have return values, perform actions, accept parameters, and more, depending on their purpose and design.

Variables and methods are essential components in Python programming. Variables store data, while methods encapsulate reusable blocks of code for specific tasks. Understanding their usage and relationship is crucial for building functional and efficient programs.

**Code used in the video:**
```python
#Variables and Methods
quote = "All is fair in love and war."
print(quote)

print(quote.upper()) #uppercase
print(quote.lower()) #lowercase
print(quote.title()) #title case
print(len(quote)) #counts characters


name = "Heath" #string
age = 33 #int
gpa = 3.7 #float - has a decimal

print(int(age))
print(int(30.1))
print(int(30.9)) - Will it round? No!

print("My name is " + name + " and I am " + str(age) + " years old.")


age +=1
print(age)

birthday = 1
age += birthday
print(age)
```