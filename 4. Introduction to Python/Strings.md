In Python, the `str` (string) data type represents a sequence of characters enclosed within single quotes (' ') or double quotes (" "). Strings in Python are immutable, which means they cannot be changed after they are created. Here are some key points about strings in Python:

Creation:

- - Example: `my_string = 'Hello, World!'` or `my_string = "Hello, World!"`

Accessing Characters:

- - You can access individual characters within a string using indexing, starting from 0.
    - Example: `print(my_string[0])` would output 'H'.

String Concatenation:

- - You can concatenate (join) two or more strings using the `+` operator.
    - Example: `greeting = 'Hello' + ' ' + 'World!'` would result in 'Hello World!'.

String Length:

- - The `len()` function can be used to determine the length (number of characters) of a string.
    - Example: `print(len(my_string))` would output the length of the string.

String Slicing:

- - You can extract a substring from a string using slicing, specifying the start and end indices.
    - Example: `substring = my_string[7:12]` would extract the substring 'World'.

String Methods:

- - Python provides various built-in methods to manipulate and transform strings. Examples include `upper()`, `lower()`, `strip()`, `split()`, `replace()`, and more.
    - Example: `print(my_string.upper())` would output 'HELLO, WORLD!'.

String Formatting:

- - String formatting allows you to embed values within a string. This can be done using the `%` operator or the `format()` method.
- Example:
```python
name = 'Alice'
age = 30
print("My name is %s and I'm %d years old." % (name, age))
# Output: My name is Alice and I'm 30 years old.
```

These are just a few key concepts related to strings in Python. Strings in Python are versatile and support a wide range of operations and manipulations.

**Code Used in the Video:**
```python
#Print string
print("Hello, world!")
print('Hello, world!')
print("""This string runs
multiple lines!""")
print("This string is "+"awesome!") #we can also concatenate
print('\n') #new line 
print('Test that new line out.')
```
