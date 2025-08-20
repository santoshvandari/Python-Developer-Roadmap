# Data Types

Python has several built-in data types that allow you to store different kinds of information. Understanding these types is crucial for effective programming.

## Strings

Strings are sequences of characters used to store text data.

**Creating Strings:**

```python
# Different ways to create strings
name = "Alice"
message = 'Hello, World!'
multiline = """This is a
multiline string
that spans several lines"""

# Empty string
empty = ""

print(name)      # Output: Alice
print(message)   # Output: Hello, World!
print(multiline) # Output: This is a
                 #         multiline string
                 #         that spans several lines
```

**String Operations:**

```python
# String concatenation
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name
print(full_name)  # Output: John Doe

# String repetition
laugh = "Ha" * 3
print(laugh)  # Output: HaHaHa

# String length
message = "Hello, Python!"
print(len(message))  # Output: 14
```

**String Indexing and Slicing:**

```python
text = "Python Programming"

# Indexing (starts from 0)
print(text[0])   # Output: P (first character)
print(text[6])   # Output: (space character)
print(text[-1])  # Output: g (last character)
print(text[-2])  # Output: n (second to last)

# Slicing [start:end:step]
print(text[0:6])    # Output: Python
print(text[7:])     # Output: Programming
print(text[:6])     # Output: Python
print(text[::2])    # Output: Pto rgamn (every 2nd character)
print(text[::-1])   # Output: gnimmargorP nohtyP (reversed)
```

**Common String Methods:**

```python
text = "  Hello, World!  "

# Case methods
print(text.upper())      # Output:   HELLO, WORLD!
print(text.lower())      # Output:   hello, world!
print(text.title())      # Output:   Hello, World!
print(text.capitalize()) # Output:   hello, world!

# Whitespace methods
print(text.strip())      # Output: Hello, World!
print(text.lstrip())     # Output: Hello, World!
print(text.rstrip())     # Output:   Hello, World!

# Search and replace
sentence = "I love Python programming"
print(sentence.find("Python"))      # Output: 7
print(sentence.replace("love", "enjoy"))  # Output: I enjoy Python programming
print(sentence.count("o"))          # Output: 2

# Split and join
words = sentence.split()
print(words)  # Output: ['I', 'love', 'Python', 'programming']
rejoined = "-".join(words)
print(rejoined)  # Output: I-love-Python-programming
```

**String Formatting:**

```python
name = "Alice"
age = 25
height = 5.6

# f-strings (Python 3.6+, recommended)
message = f"My name is {name}, I'm {age} years old and {height} feet tall"
print(message)

# .format() method
message = "My name is {}, I'm {} years old".format(name, age)
print(message)

# % formatting (older style)
message = "My name is %s, I'm %d years old" % (name, age)
print(message)

# Advanced f-string formatting
pi = 3.14159
print(f"Pi rounded to 2 decimals: {pi:.2f}")  # Output: Pi rounded to 2 decimals: 3.14
```

## Numbers

Python supports different types of numbers: integers, floating-point numbers, and complex numbers.

**Integers:**

```python
# Integer creation
age = 25
negative = -10
large_number = 1000000

# Integer operations
a = 10
b = 3

print(a + b)   # Addition: 13
print(a - b)   # Subtraction: 7
print(a * b)   # Multiplication: 30
print(a / b)   # Division: 3.3333333333333335
print(a // b)  # Floor division: 3
print(a % b)   # Modulus (remainder): 1
print(a ** b)  # Exponentiation: 1000

# Large integers (Python handles automatically)
big_number = 123456789012345678901234567890
print(big_number)  # Python can handle arbitrarily large integers
```

**Floating-Point Numbers:**

```python
# Float creation
height = 5.9
temperature = -2.5
scientific = 1.5e-4  # Scientific notation: 0.00015

# Float operations
x = 10.5
y = 2.5

print(x + y)   # Output: 13.0
print(x / y)   # Output: 4.2
print(round(x / 3, 2))  # Round to 2 decimal places: 3.5

# Be careful with float precision
print(0.1 + 0.2)  # Output: 0.30000000000000004 (not exactly 0.3)

# Use round() for display
result = 0.1 + 0.2
print(round(result, 1))  # Output: 0.3
```

**Type Conversion:**

```python
# Converting between number types
integer_num = 42
float_num = 3.14
string_num = "123"

# Convert to different types
print(float(integer_num))  # Output: 42.0
print(int(float_num))      # Output: 3 (truncates decimal)
print(int(string_num))     # Output: 123
print(str(integer_num))    # Output: "42"

# Check number types
print(type(integer_num))   # Output: <class 'int'>
print(type(float_num))     # Output: <class 'float'>
```

## Booleans

Booleans represent truth values: True or False.

**Boolean Values:**

```python
# Boolean literals
is_sunny = True
is_raining = False

print(is_sunny)   # Output: True
print(is_raining) # Output: False
print(type(is_sunny))  # Output: <class 'bool'>
```

**Boolean Operations:**

```python
# Logical operators
a = True
b = False

print(a and b)  # Output: False (both must be True)
print(a or b)   # Output: True (at least one must be True)
print(not a)    # Output: False (opposite of a)
print(not b)    # Output: True (opposite of b)

# Comparison operations return booleans
print(5 > 3)    # Output: True
print(10 == 10) # Output: True
print(7 != 7)   # Output: False
```

**Truthiness in Python:**

```python
# Values that are considered False
print(bool(0))        # Output: False
print(bool(""))       # Output: False (empty string)
print(bool([]))       # Output: False (empty list)
print(bool(None))     # Output: False

# Values that are considered True
print(bool(1))        # Output: True
print(bool("hello"))  # Output: True (non-empty string)
print(bool([1, 2]))   # Output: True (non-empty list)
print(bool(-1))       # Output: True (any non-zero number)
```

## Lists

Lists are ordered collections that can store multiple items of different types.

**Creating Lists:**

```python
# Different ways to create lists
numbers = [1, 2, 3, 4, 5]
names = ["Alice", "Bob", "Charlie"]
mixed = [1, "hello", 3.14, True]
empty_list = []

print(numbers)  # Output: [1, 2, 3, 4, 5]
print(mixed)    # Output: [1, 'hello', 3.14, True]
```

**List Operations:**

```python
fruits = ["apple", "banana", "orange"]

# Accessing elements (indexing)
print(fruits[0])   # Output: apple
print(fruits[-1])  # Output: orange (last element)

# Slicing
print(fruits[0:2])  # Output: ['apple', 'banana']
print(fruits[1:])   # Output: ['banana', 'orange']

# List length
print(len(fruits))  # Output: 3

# Check if item exists
print("apple" in fruits)     # Output: True
print("grape" in fruits)     # Output: False
```

**Modifying Lists:**

```python
colors = ["red", "green", "blue"]

# Adding elements
colors.append("yellow")        # Add to end
print(colors)  # Output: ['red', 'green', 'blue', 'yellow']

colors.insert(1, "purple")     # Insert at index 1
print(colors)  # Output: ['red', 'purple', 'green', 'blue', 'yellow']

# Removing elements
colors.remove("purple")        # Remove by value
print(colors)  # Output: ['red', 'green', 'blue', 'yellow']

removed = colors.pop()         # Remove and return last element
print(removed)  # Output: yellow
print(colors)   # Output: ['red', 'green', 'blue']

# Modifying elements
colors[0] = "crimson"
print(colors)  # Output: ['crimson', 'green', 'blue']
```

**List Methods:**

```python
numbers = [3, 1, 4, 1, 5, 9, 2, 6]

# Sorting
numbers.sort()
print(numbers)  # Output: [1, 1, 2, 3, 4, 5, 6, 9]

# Reversing
numbers.reverse()
print(numbers)  # Output: [9, 6, 5, 4, 3, 2, 1, 1]

# Counting and finding
print(numbers.count(1))    # Output: 2
print(numbers.index(5))    # Output: 2 (first occurrence)

# Extending lists
more_numbers = [7, 8]
numbers.extend(more_numbers)
print(numbers)  # Output: [9, 6, 5, 4, 3, 2, 1, 1, 7, 8]
```

## Tuples

Tuples are ordered collections like lists, but they are immutable (cannot be changed after creation).

**Creating Tuples:**

```python
# Different ways to create tuples
coordinates = (3, 4)
colors = ("red", "green", "blue")
mixed_tuple = (1, "hello", 3.14)
single_item = (42,)  # Note the comma for single-item tuple
empty_tuple = ()

print(coordinates)  # Output: (3, 4)
print(type(coordinates))  # Output: <class 'tuple'>
```

**Tuple Operations:**

```python
point = (10, 20, 30)

# Accessing elements
print(point[0])   # Output: 10
print(point[-1])  # Output: 30

# Slicing
print(point[0:2])  # Output: (10, 20)

# Length and membership
print(len(point))      # Output: 3
print(20 in point)     # Output: True

# Unpacking tuples
x, y, z = point
print(f"x={x}, y={y}, z={z}")  # Output: x=10, y=20, z=30
```

**When to Use Tuples:**

```python
# Tuples are great for:
# 1. Coordinates
position = (100, 200)

# 2. RGB colors
red = (255, 0, 0)

# 3. Database records
person = ("John", "Doe", 30, "Engineer")

# 4. Function returns (multiple values)
def get_name_age():
    return "Alice", 25

name, age = get_name_age()
print(f"{name} is {age} years old")  # Output: Alice is 25 years old
```

## Dictionaries

Dictionaries store data in key-value pairs and are unordered collections.

**Creating Dictionaries:**

```python
# Different ways to create dictionaries
person = {"name": "Alice", "age": 30, "city": "New York"}
grades = dict(math=95, science=87, english=92)
empty_dict = {}

print(person)  # Output: {'name': 'Alice', 'age': 30, 'city': 'New York'}
print(grades)  # Output: {'math': 95, 'science': 87, 'english': 92}
```

**Dictionary Operations:**

```python
student = {"name": "Bob", "age": 20, "major": "Computer Science"}

# Accessing values
print(student["name"])        # Output: Bob
print(student.get("age"))     # Output: 20
print(student.get("gpa", 0))  # Output: 0 (default if key doesn't exist)

# Adding/modifying values
student["gpa"] = 3.8
student["age"] = 21
print(student)  # Output: {'name': 'Bob', 'age': 21, 'major': 'Computer Science', 'gpa': 3.8}

# Removing values
del student["major"]
removed_gpa = student.pop("gpa")
print(student)      # Output: {'name': 'Bob', 'age': 21}
print(removed_gpa)  # Output: 3.8
```

**Dictionary Methods:**

```python
inventory = {"apples": 50, "bananas": 30, "oranges": 25}

# Getting keys, values, and items
print(inventory.keys())    # Output: dict_keys(['apples', 'bananas', 'oranges'])
print(inventory.values())  # Output: dict_values([50, 30, 25])
print(inventory.items())   # Output: dict_items([('apples', 50), ('bananas', 30), ('oranges', 25)])

# Iterating through dictionary
for fruit, quantity in inventory.items():
    print(f"{fruit}: {quantity}")

# Output:
# apples: 50
# bananas: 30
# oranges: 25

# Checking for keys
print("apples" in inventory)     # Output: True
print("grapes" in inventory)     # Output: False
```

## Sets

Sets are unordered collections of unique elements.

**Creating Sets:**

```python
# Different ways to create sets
numbers = {1, 2, 3, 4, 5}
colors = set(["red", "green", "blue", "red"])  # Duplicates removed
empty_set = set()  # Note: {} creates an empty dict, not set

print(numbers)  # Output: {1, 2, 3, 4, 5}
print(colors)   # Output: {'blue', 'green', 'red'}
```

**Set Operations:**

```python
fruits = {"apple", "banana", "orange"}

# Adding elements
fruits.add("grape")
print(fruits)  # Output: {'grape', 'banana', 'orange', 'apple'}

# Removing elements
fruits.remove("banana")  # Raises error if not found
fruits.discard("kiwi")   # No error if not found
print(fruits)  # Output: {'grape', 'orange', 'apple'}

# Set operations
set1 = {1, 2, 3, 4}
set2 = {3, 4, 5, 6}

print(set1.union(set2))        # Output: {1, 2, 3, 4, 5, 6}
print(set1.intersection(set2)) # Output: {3, 4}
print(set1.difference(set2))   # Output: {1, 2}
```

## Practice Exercise - Data Types

```python
def data_types_demo():
    """Demonstrate all Python data types with practical examples."""

    # String data
    name = "Python Learner"
    print(f"Welcome, {name}!")

    # Numeric data
    score = 95
    percentage = score / 100
    print(f"Your score: {score} ({percentage:.1%})")

    # Boolean data
    passed = score >= 60
    print(f"Passed: {passed}")

    # List data
    subjects = ["Math", "Science", "English"]
    subjects.append("History")
    print(f"Subjects: {subjects}")

    # Tuple data (immutable)
    coordinates = (10, 20)
    x, y = coordinates
    print(f"Position: x={x}, y={y}")

    # Dictionary data
    grades = {"Math": 95, "Science": 87, "English": 92}
    grades["History"] = 89
    print("Grades:")
    for subject, grade in grades.items():
        print(f"  {subject}: {grade}")

    # Set data (unique values)
    unique_scores = {95, 87, 92, 89, 95, 87}  # Duplicates removed
    print(f"Unique scores: {sorted(unique_scores)}")

# Run the demonstration
data_types_demo()
```

## Key Takeaways

- Strings store text and have many useful methods
- Numbers include integers and floats with standard math operations
- Booleans represent True/False and are used in conditions
- Lists are mutable ordered collections
- Tuples are immutable ordered collections
- Dictionaries store key-value pairs
- Sets store unique unordered elements
- Choose the right data type for your specific needs

## What's Next?

Now that you understand Python's data types, you're ready to learn how to work with them using operators. Let's move on to [Operators](04-operators.md)!