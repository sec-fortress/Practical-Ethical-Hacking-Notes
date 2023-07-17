In Python, you can read from and write to files using file objects and various methods provided by the built-in `open()` function. Here's an explanation of reading from and writing to files in Python:

Reading Files:

To read from a file, you need to open it in read mode using the `open()` function. Once the file is open, you can use methods like `read()`, `readline()`, or `readlines()` to retrieve the contents of the file.

- `read()`: Reads the entire content of the file as a string.
- `readline()`: Reads a single line from the file.
- `readlines()`: Reads all lines from the file and returns them as a list.

Here's an example of reading from a file:
```python
# Open the file in read mode
file = open("example.txt", "r")


# Read the entire content
content = file.read()
print(content)


# Read a single line
line = file.readline()
print(line)


# Read all lines
lines = file.readlines()
print(lines)


# Close the file, this is very important after each arguments
file.close()
```

Writing Files:

To write to a file, you need to open it in write mode using the `open()` function. Once the file is open, you can use the `write()` method to write content to the file.

- `write(content)`: Writes the specified content to the file.

Here's an example of writing to a file:
```python
# Open the file in write mode
file = open("example.txt", "w")


# Write content to the file
file.write("Hello, World!\n")
file.write("This is a new line.")


# Close the file, always remember to do this 
file.close()
```

Appending to Files:

To append content to an existing file without overwriting its existing contents, you can open the file in append mode (`"a"`) using the `open()` function. Then, you can use the `write()` method to append content to the file.
```python
# Open the file in append mode
file = open("example.txt", "a")


# Append content to the file
file.write("\nThis is appended content.")


# Close the file
file.close()
```

It is generally recommended to use the `with` statement when working with files. This ensures that the file is properly closed even if an exception occurs.
```python
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

Reading and writing files in Python allows you to handle external data, process large amounts of information, and store program outputs for later use. It is important to properly manage file resources and close them after use to avoid memory leaks and ensure data integrity.