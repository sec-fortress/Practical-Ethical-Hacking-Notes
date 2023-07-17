In Python, a list is a versatile and mutable data structure that can hold a collection of items. It allows you to store multiple values of different data types in a single variable. Here's an explanation of lists in Python:

List Creation:

To create a list, you enclose comma-separated values within square brackets `[ ]`. Here's an example:

```
fruits = ["apple", "banana", "orange"] 
```

List Access:

You can access individual elements in a list using indexing. Indexing starts from 0 for the first element and goes up to the length of the list minus one. Here are some examples:
```
print(fruits[0])    # Output: "apple"
print(fruits[2])    # Output: "orange"
```

List Modification:

Lists are mutable, which means you can modify their elements. You can assign new values to specific positions in the list or use methods to modify the list itself. Here are some examples:

```
fruits[1] = "grape"     # Modifying an element
fruits.append("kiwi")   # Adding an element to the end
fruits.remove("apple")  # Removing an element
```

List Operations:

Python provides various operations that can be performed on lists. Some common operations include:

- Concatenation: You can use the `+` operator to concatenate two or more lists.
- Length: The `len()` function returns the number of elements in a list.
- Slicing: You can extract a sublist from a list using slicing.
- Iteration: You can use a loop to iterate over the elements of a list.

Here are some examples:

```python
fruits = ["apple", "banana", "orange"]
fruits2 = ["grape", "kiwi"]


combined = fruits + fruits2
print(combined)         # Output: ["apple", "banana", "orange", "grape", "kiwi"]


print(len(fruits))      # Output: 3


sublist = fruits[1:3]
print(sublist)          # Output: ["banana", "orange"]


for fruit in fruits:
    print(fruit)        # Output: "apple", "banana", "orange"
```

Lists are powerful data structures in Python that allow you to store and manipulate collections of items. They are widely used for managing and processing data in various applications.

Here is how it was used in the tutorial:
```python
#Lists - Have brackets []
movies = ["When Harry Met Sally", "The Hangover", "The Perks of Being a Wallflower", "The Exorcist"]

print(movies[1]) #returns the second item in the list - index / indices
print(movies[0]) #returns the first item in the list
print(movies[1:3]) #returns the first number given until right before last number given
print(movies[1:4]) #returns all 
print(movies[1:]) #returns everything from number to end of list
print(movies[:1]) #everything before 1
print(movies[:2])
print(movies[-1]) #grabs last item

print(len(movies)) #counts items in list
movies.append("JAWS")
print(movies) #appends to end of list

movies.insert(2, "Hustle")
print(movies)

movies.pop() #removes last item
print(movies)

movies.pop(0) #removes first item 
print(movies)

amber_movies = ['Just Go With It', '50 First Dates']
our_favorite_movies = movies + amber_movies
print(our_favorite_movies)

grades = [["Bob", 82], ["Alice", 90], ["Jeff", 73]]
bobs_grade = grades[0][1]
print(bobs_grade)
grades[0][1] = 83
print(bobs_grade)
```
