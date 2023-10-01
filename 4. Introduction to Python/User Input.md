In Python, you can interact with the user and receive input using the `input()` function. The `input()` function allows you to prompt the user for input and receive the input as a string. Here's an explanation of user input in Python:
```python
name = input("Enter your name: ")
print("Hello, " + name + "!")
```

In this example, the `input()` function is used to prompt the user to enter their name. The message "Enter your name: " is displayed to the user as a prompt. The user can then type their name and press Enter. The input provided by the user is stored in the variable `name`, and the program prints a greeting using the entered name.

The `input()` function always returns the user's input as a string. If you need to convert the input to a different data type, such as an integer or float, you can use appropriate conversion functions like `int()` or `float()`.
```python
age = input("Enter your age: ")
age = int(age)  # Convert the input to an integer


print("You will be " + str(age + 1) + " next year.")
```

In this example, the user is asked to enter their age. The input is stored as a string in the variable `age`. To perform arithmetic calculations, the input is converted to an integer using the `int()` function. The program then adds 1 to the age and prints the result.

When using user input, keep in mind that it is a string by default. Ensure proper validation and error handling if you expect specific data types or want to handle invalid input.

User input allows you to make your programs interactive and dynamic by accepting input from users during runtime. It provides a way to customize program behavior based on user responses.

How it was used:
```python
#USER INPUT

x = float(input("Give me a number: "))
o = input("Give me an operator: ")
y = float(input("Give me yet another number: "))

if o == "+":
	print(x + y)
elif o == "-":
	print(x - y)
elif o == "/":
	print(x / y)
elif o == "*":
	print(x * y)
elif o == "**":
	print(x ** y)
else:
	print("Unknown operator.")
```

