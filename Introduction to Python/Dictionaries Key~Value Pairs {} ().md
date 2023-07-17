In Python, a dictionary is an unordered collection of key-value pairs. It is a versatile and powerful data structure that allows you to store, retrieve, and manipulate data based on unique keys. Here's an explanation of dictionaries in Python:

Dictionary Creation:

To create a dictionary, you enclose key-value pairs within curly braces `{ }`, separating each pair with a colon `:`. Here's an example:
```python
student = {
    "name": "Alice",
    "age": 20,
    "major": "Computer Science"
}
```

Dictionary Access:

You can access the values in a dictionary by referring to their corresponding keys. Keys provide a way to uniquely identify and retrieve values. Here's an example:
```python
print(student["name"])   # Output: "Alice"
print(student["age"])    # Output: 20
```

Dictionary Modification:

Dictionaries are mutable, which means you can modify their values by assigning new values to specific keys. Here's an example:
```python
student["age"] = 21       # Modifying a value
student["city"] = "London"    # Adding a new key-value pair
```

Dictionary Operations:

Python provides various operations that can be performed on dictionaries. Some common operations include:

- Length: The `len()` function returns the number of key-value pairs in a dictionary.
- Iteration: You can iterate over the keys, values, or key-value pairs of a dictionary using loops.
- Deletion: You can remove a key-value pair from a dictionary using the `del` keyword.

Here are some examples:
```python
student = {
    "name": "Alice",
    "age": 20,
    "major": "Computer Science"
}


print(len(student))          # Output: 3


for key in student:
    print(key, student[key])  # Output: "name Alice", "age 20", "major Computer Science"


del student["age"]           # Deleting a key-value pair
```

Dictionaries are powerful data structures that provide a flexible way to store and retrieve data based on keys. They are commonly used for organizing and manipulating data that requires quick and efficient access.

Used:
```python
#DICTIONARIES - key/value pairs {}

drinks = {"White Russian": 7, "Old Fashion": 10, "Lemon Drop": 8} #drink is key, price is value
print(drinks)

employees = {"Finance": ["Bob", "Linda", "Tina"], "IT": ["Gene", "Louise", "Teddy"], "HR": ["Jimmy Jr.", "Mort"]}
employees['Legal'] = ["Mr. Frond"] #adds new key:value pair
print(employees)

employees.update({"Sales": ["Andie", "Ollie"]}) #adds new key:value pair
print(employees)

drinks['White Russian'] = 8
print(drinks)

print(drinks.get("White Russian"))
```