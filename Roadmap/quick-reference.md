# Quick Reference Cheat Sheet

## Essential Python Syntax

```python
# Variables and Data Types
name = "Alice"              # String
age = 30                    # Integer
height = 5.6               # Float
is_student = True          # Boolean
numbers = [1, 2, 3]        # List
coordinates = (10, 20)     # Tuple
person = {"name": "Bob"}   # Dictionary
unique_items = {1, 2, 3}   # Set

# Control Structures
if condition:
    # do something
elif other_condition:
    # do something else
else:
    # default action

for item in iterable:
    # process item

while condition:
    # repeat while true

# Functions
def function_name(param1, param2="default"):
    """Function docstring."""
    return param1 + param2

# Classes
class MyClass:
    def __init__(self, value):
        self.value = value
    
    def method(self):
        return self.value

# Exception Handling
try:
    # risky operation
    pass
except SpecificError as e:
    # handle specific error
    pass
except Exception as e:
    # handle any other error
    pass
finally:
    # cleanup code
    pass
```

## Common Built-in Functions

```python
# Type conversion
int("123")          # String to integer
float("3.14")       # String to float
str(42)             # Number to string
list("hello")       # String to list: ['h', 'e', 'l', 'l', 'o']

# Sequence operations
len([1, 2, 3])      # Length: 3
max([1, 5, 3])      # Maximum: 5
min([1, 5, 3])      # Minimum: 1
sum([1, 2, 3])      # Sum: 6
sorted([3, 1, 2])   # Sorted: [1, 2, 3]
reversed([1, 2, 3]) # Reversed iterator

# Iteration
enumerate(['a', 'b', 'c'])  # [(0, 'a'), (1, 'b'), (2, 'c')]
zip([1, 2], ['a', 'b'])     # [(1, 'a'), (2, 'b')]
range(5)                    # 0, 1, 2, 3, 4
```

## String Methods Quick Reference

```python
text = "  Hello, World!  "
text.strip()           # Remove whitespace: "Hello, World!"
text.lower()           # Lowercase: "  hello, world!  "
text.upper()           # Uppercase: "  HELLO, WORLD!  "
text.replace("Hello", "Hi")  # Replace: "  Hi, World!  "
text.split(",")        # Split: ["  Hello", " World!  "]
"".join(["a", "b"])    # Join: "ab"
"Hello".startswith("H") # True
"World".endswith("d")   # True
```

## List Methods Quick Reference

```python
lst = [1, 2, 3]
lst.append(4)          # Add to end: [1, 2, 3, 4]
lst.insert(0, 0)       # Insert at index: [0, 1, 2, 3, 4]
lst.remove(2)          # Remove by value: [0, 1, 3, 4]
lst.pop()              # Remove and return last: 4
lst.index(3)           # Find index of value: 2
lst.count(1)           # Count occurrences: 1
lst.sort()             # Sort in place
lst.reverse()          # Reverse in place
```

## Dictionary Methods Quick Reference

```python
d = {"a": 1, "b": 2}
d.keys()               # dict_keys(['a', 'b'])
d.values()             # dict_values([1, 2])
d.items()              # dict_items([('a', 1), ('b', 2)])
d.get("c", 0)          # Get with default: 0
d.pop("a")             # Remove and return: 1
d.update({"c": 3})     # Add/update: {"b": 2, "c": 3}
```

## Common Error Types

- `SyntaxError` - Invalid Python syntax
- `NameError` - Variable not defined
- `TypeError` - Wrong data type for operation
- `ValueError` - Right type, wrong value
- `IndexError` - List index out of range
- `KeyError` - Dictionary key not found
- `FileNotFoundError` - File doesn't exist
- `ImportError` - Module can't be imported

## File Operations

```python
# Reading files
with open("file.txt", "r") as f:
    content = f.read()

# Writing files
with open("file.txt", "w") as f:
    f.write("Hello, World!")

# Appending to files
with open("file.txt", "a") as f:
    f.write("New line")
```

## List Comprehensions

```python
# Basic list comprehension
squares = [x**2 for x in range(10)]

# With condition
even_squares = [x**2 for x in range(10) if x % 2 == 0]

# Dictionary comprehension
square_dict = {x: x**2 for x in range(5)}

# Set comprehension
unique_lengths = {len(word) for word in ["hello", "world", "python"]}
```

## Lambda Functions

```python
# Basic lambda
square = lambda x: x**2

# With map
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x**2, numbers))

# With filter
evens = list(filter(lambda x: x % 2 == 0, numbers))

# With sort
students = [("Alice", 85), ("Bob", 90), ("Charlie", 78)]
students.sort(key=lambda x: x[1])  # Sort by grade
```

## Common Patterns

```python
# Check if file exists
import os
if os.path.exists("file.txt"):
    print("File exists")

# Get current date/time
from datetime import datetime
now = datetime.now()
print(now.strftime("%Y-%m-%d %H:%M:%S"))

# Random operations
import random
random_number = random.randint(1, 100)
random_choice = random.choice(["apple", "banana", "cherry"])

# JSON operations
import json
data = {"name": "Alice", "age": 30}
json_string = json.dumps(data)
parsed_data = json.loads(json_string)
```

## Debugging Tips

```python
# Print debugging
print(f"Debug: variable = {variable}")

# Type checking
print(f"Type of variable: {type(variable)}")

# Check if variable exists
try:
    print(variable)
except NameError:
    print("Variable not defined")

# Use assert for debugging
assert len(my_list) > 0, "List should not be empty"
```

## Performance Tips

- Use list comprehensions instead of loops when possible
- Use `join()` for string concatenation instead of `+`
- Use `set` for membership testing instead of `list`
- Use generators for large datasets
- Use built-in functions like `sum()`, `max()`, `min()`
- Cache expensive function results with `@lru_cache`