In Python, classes and objects are key components of object-oriented programming (OOP). They provide a way to structure code and define custom data types. Here's an explanation of classes and objects in Python:

Classes:

A class is a blueprint or a template for creating objects. It defines the properties (attributes) and behaviors (methods) that objects of that class will possess. You can think of a class as a blueprint for creating instances of objects with similar characteristics and functionalities. Here's an example of a simple class definition:
```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age


    def bark(self):
        print("Woof!")


    def display_info(self):
        print("Name:", self.name)
        print("Age:", self.age)
```

In this example, the `Dog` class has attributes `name` and `age`, and methods `bark()` and `display_info()`. The `__init__()` method is a special method known as the constructor, which is called when an object of the class is created.

Objects:

An object is an instance of a class. It is created based on the blueprint provided by the class. Each object has its own set of attributes and can invoke the methods defined in the class. You create objects by calling the class as if it were a function. Here's an example:
```python
# Create objects of the Dog class
dog1 = Dog("Buddy", 5)
dog2 = Dog("Max", 3)


# Call methods on the objects
dog1.bark()               # Output: "Woof!"
dog1.display_info()       # Output: "Name: Buddy", "Age: 5"


dog2.bark()               # Output: "Woof!"
dog2.display_info()       # Output: "Name: Max", "Age: 3"
```

In this example, `dog1` and `dog2` are objects created from the `Dog` class. Each object has its own set of attributes (`name` and `age`) and can invoke the methods (`bark()` and `display_info()`) defined in the class.

Classes and objects are essential in object-oriented programming as they provide a way to organize code, encapsulate data, and define reusable entities. They enable you to model real-world entities, create custom data types, and build complex systems by leveraging the principles of inheritance, polymorphism, and encapsulation.

*How it was used:*
> We first of all need to create a **class** python with the following code:
```python
class Employees:

	def __init__(self, name, department, role, salary, years_employed):
		self.name = name
		self.department = department
		self.role = role
		self.salary = salary
		self.years_employed = years_employed
		
	def eligible_for_retirement(self):
		if self.years_employed >= 20:
			return True
		else:
			return False
```

> Then we can successfully create another python file with **objects**
```python
from Employees import Employees

e1 = Employees("Bob", "Sales", "Director of Sales", 100000, 20)
e2 = Employees("Linda", "Executive", "CIO", 150000, 10)

print(e1.name)
print(e2.role)
print(e1.eligible_for_retirement())
```