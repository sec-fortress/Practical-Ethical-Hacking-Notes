In Python, importing modules allows you to access and use code that resides in external Python files or libraries. Modules are a way to organize and reuse code, making it easier to manage and maintain large projects. Here's an explanation of importing modules in Python:

Importing Entire Modules:
To import an entire module, you use the import keyword followed by the module name. Here's an example:
```python
import math


result = math.sqrt(25)
print(result)   # Output: 5.0
In this example, the math module is imported, and the sqrt() function from the module is used to calculate the square root of 25.
```

Importing Specific Functions or Variables:
If you only need to use specific functions or variables from a module, you can import them directly. Here's an example:
```python
from math import sqrt


result = sqrt(25)
print(result)   # Output: 5.0
In this case, only the sqrt() function is imported from the math module, so you can use it directly without prefixing it with the module name.
```


Importing Modules with an Alias:
You can also import a module and give it an alias using the as keyword. This can be helpful when dealing with modules with long names or to avoid naming conflicts. Here's an example:
```python
import math as m


result = m.sqrt(25)
print(result)   # Output: 5.0
```

In this example, the math module is imported and assigned the alias m, so you can use m.sqrt() instead of math.sqrt().

Importing All Functions and Variables:
If you want to import all functions and variables from a module, you can use the * wildcard character. However, it is generally recommended to import only what you need to avoid namespace pollution. Here's an example:
```python
from math import *


result = sqrt(25)
print(result)   # Output: 5.0
```

In this case, all functions and variables from the math module are imported directly, allowing you to use them without prefixing with the module name.

Importing modules enables you to access and utilize a wide range of functionality provided by the Python standard library or third-party libraries. It promotes code reusability, modularity, and maintainability in your Python programs.

How it was used:
```python
#IMPORTING - Importing is important.
import sys #system functions and parameters
from datetime import datetime as dt #import with alias 

print(sys.version)
print(dt.now())
```

