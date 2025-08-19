# Complete Python Learning Guide

A comprehensive resource for learning Python programming from beginner to advanced level. This guide provides structured content, practical code examples, syntax explanations, and progressive learning paths to help you master Python programming concepts systematically.

## How to Use This Guide

This guide is organized into progressive skill levels, each building upon the previous one. You can:

- Start from the beginning if you're new to programming
- Jump to specific sections based on your current knowledge
- Use the code examples to practice and experiment
- Follow the suggested exercises to reinforce your learning

**Tip**: All code examples in this guide are designed to be runnable. Copy them into your Python environment and experiment!

## Table of Contents

### [Getting Started](#getting-started)

- [Why Python?](#why-python)
- [Installation](#installation)
- [Your First Python Program](#your-first-python-program)
- [Development Environment Setup](#development-environment-setup)

### [Beginner Level](#beginner-level)

- [Basic Syntax](#basic-syntax)
  - [Variables and Naming](#variables-and-naming)
  - [Comments and Documentation](#comments-and-documentation)
  - [Code Structure and Indentation](#code-structure-and-indentation)
- [Data Types](#data-types)
  - [Strings](#strings)
  - [Numbers (Integers and Floats)](#numbers)
  - [Booleans](#booleans)
  - [Lists](#lists)
  - [Tuples](#tuples)
  - [Dictionaries](#dictionaries)
  - [Sets](#sets)
- [Operators](#operators)
  - [Arithmetic Operators](#arithmetic-operators)
  - [Comparison Operators](#comparison-operators)
  - [Logical Operators](#logical-operators)
  - [Assignment Operators](#assignment-operators)
- [Input and Output](#input-and-output)
  - [Getting User Input](#getting-user-input)
  - [Printing Output](#printing-output)

### [Intermediate Level](#intermediate-level)

- [Control Structures](#control-structures)
  - [If/Elif/Else Statements](#conditional-statements)
  - [For Loops](#for-loops)
  - [While Loops](#while-loops)
  - [Break and Continue](#break-and-continue)
  - [Nested Loops](#nested-loops)
- [Functions](#functions)
  - [Function Definition](#function-definition)
  - [Parameters and Arguments](#parameters-and-arguments)
  - [Return Values](#return-values)
  - [Variable Scope](#variable-scope)
  - [Lambda Functions](#lambda-functions)
  - [Function Documentation](#function-documentation)
- [Error Handling](#error-handling)
  - [Try/Except Blocks](#try-except-blocks)
  - [Common Exception Types](#common-exception-types)
  - [Finally Blocks](#finally-blocks)
  - [Custom Exceptions](#custom-exceptions)
  - [Debugging Techniques](#debugging-techniques)
- [Modules and Packages](#modules-and-packages)
  - [Importing Modules](#importing-modules)
  - [Creating Custom Modules](#creating-custom-modules)
  - [Package Structure](#package-structure)
  - [Standard Library Overview](#standard-library-overview)
  - [Virtual Environments](#virtual-environments)

### [Advanced Level](#advanced-level)

- [Object-Oriented Programming](#object-oriented-programming)
  - [Classes and Objects](#classes-and-objects)
  - [Attributes and Methods](#attributes-and-methods)
  - [Inheritance](#inheritance)
  - [Polymorphism](#polymorphism)
  - [Encapsulation](#encapsulation)
  - [Special Methods](#special-methods)
- [Advanced Features](#advanced-features)
  - [Decorators](#decorators)
  - [Generators](#generators)
  - [Context Managers](#context-managers)
  - [List Comprehensions](#list-comprehensions)
  - [Iterators](#iterators)
  - [Advanced Function Features](#advanced-function-features)
- [File Handling](#file-handling)
  - [Reading and Writing Files](#reading-and-writing-files)
  - [Working with CSV Files](#working-with-csv-files)
  - [JSON File Operations](#json-file-operations)
  - [File Paths with Pathlib](#file-paths-with-pathlib)
  - [Binary Files](#binary-files)
  - [File System Operations](#file-system-operations)

### [Professional Level](#professional-level)

- [Popular Libraries](#popular-libraries)
  - [NumPy for Numerical Computing](#numpy-for-numerical-computing)
  - [Pandas for Data Manipulation](#pandas-for-data-manipulation)
  - [Requests for HTTP Operations](#requests-for-http-operations)
  - [Matplotlib for Data Visualization](#matplotlib-for-data-visualization)
  - [Web Frameworks (Flask/Django)](#web-frameworks)
  - [Database Connectivity](#database-connectivity)
- [Best Practices](#best-practices)
  - [PEP 8 Style Guide](#pep-8-style-guide)
  - [Code Organization](#code-organization)
  - [Testing with unittest and pytest](#testing)
  - [Version Control with Git](#version-control-with-git)
  - [Performance Optimization](#performance-optimization)
  - [Logging and Debugging](#logging-and-debugging)

### [Resources and Next Steps](#resources-and-next-steps)

- [Practice Exercises](#practice-exercises)
- [Project Ideas](#project-ideas)
- [External Resources](#external-resources)
- [Community and Learning Platforms](#community-and-learning-platforms)
- [Career Paths](#career-paths)
- [Troubleshooting Guide](#troubleshooting-guide)

---

## Getting Started

### Why Python?

Python is one of the most popular and versatile programming languages in the world. Here's why it's perfect for beginners and professionals alike:

**Easy to Learn**

- Simple, readable syntax that resembles natural language
- Minimal set to start coding
- Extensive documentation and community support

**Versatile Applications**

- Web development (Django, Flask)
- Data science and machine learning (NumPy, Pandas, TensorFlow)
- Automation and scripting
- Desktop applications
- Game development
- Scientific computing

**Career Opportunities**

- High demand in job market
- Used by major companies: Google, Netflix, Instagram, Spotify
- Average salary ranges from $70k-$150k+ depending on experience

### Installation

#### Windows

1. **Download Python**

   - Visit [python.org](https://python.org/downloads/)
   - Download the latest Python 3.x version (3.8 or higher recommended)
   - Choose "Windows installer (64-bit)" for most systems

2. **Install Python**

   - Run the downloaded installer
   - ⚠️ **IMPORTANT**: Check "Add Python to PATH" during installation
   - Click "Install Now"
   - Wait for installation to complete

3. **Verify Installation**
   ```bash
   # Open Command Prompt and type:
   python --version
   # Should display: Python 3.x.x
   ```

#### macOS

1. **Using Homebrew (Recommended)**

   ```bash
   # Install Homebrew if you don't have it
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

   # Install Python
   brew install python
   ```

2. **Using Official Installer**

   - Visit [python.org](https://python.org/downloads/)
   - Download the macOS installer
   - Run the installer and follow instructions

3. **Verify Installation**
   ```bash
   python3 --version
   # Should display: Python 3.x.x
   ```

#### Linux (Ubuntu/Debian)

```bash
# Update package list
sudo apt update

# Install Python 3 and pip
sudo apt install python3 python3-pip

# Verify installation
python3 --version
pip3 --version
```

#### Linux (CentOS/RHEL/Fedora)

```bash
# For CentOS/RHEL
sudo yum install python3 python3-pip

# For Fedora
sudo dnf install python3 python3-pip

# Verify installation
python3 --version
pip3 --version
```

### Your First Python Program

Let's write your first Python program! This traditional "Hello, World!" program will verify that Python is working correctly.

#### Method 1: Interactive Python Shell

```bash
# Open terminal/command prompt and type:
python
# or on some systems:
python3
```

You'll see the Python prompt (`>>>`). Now type:

```python
>>> print("Hello, World!")
Hello, World!
>>> print("Welcome to Python!")
Welcome to Python!
>>> exit()
```

#### Method 2: Python Script File

1. **Create a new file** called `hello.py`
2. **Add this code**:

   ```python
   # My first Python program
   print("Hello, World!")
   print("My name is [Your Name]")
   print("I'm learning Python!")

   # Let's do some basic math
   print("2 + 3 =", 2 + 3)
   print("10 - 4 =", 10 - 4)
   print("5 * 6 =", 5 * 6)
   print("15 / 3 =", 15 / 3)
   ```

3. **Run the program**:
   ```bash
   python hello.py
   # or
   python3 hello.py
   ```

**Expected Output:**

```
Hello, World!
My name is [Your Name]
I'm learning Python!
2 + 3 = 5
10 - 4 = 6
5 * 6 = 30
15 / 3 = 5.0
```

**Congratulations!** You've just written and executed your first Python program!

### Development Environment Setup

While you can write Python code in any text editor, using a proper development environment will make your coding experience much better.

#### Recommended IDEs and Editors

**For Beginners:**

- **IDLE** (comes with Python)

  - Built-in Python editor
  - Simple and lightweight
  - Good for learning basics

- **Thonny** (Free)
  - Designed specifically for beginners
  - Built-in debugger and variable inspector
  - Download from [thonny.org](https://thonny.org)

**For Intermediate/Advanced:**

- **Visual Studio Code** (Free)

  - Excellent Python extension
  - IntelliSense and debugging
  - Download from [code.visualstudio.com](https://code.visualstudio.com)

- **PyCharm** (Free Community Edition)
  - Professional Python IDE
  - Advanced debugging and testing tools
  - Download from [jetbrains.com/pycharm](https://jetbrains.com/pycharm)

#### Setting Up Visual Studio Code for Python

1. **Install VS Code**

   - Download from [code.visualstudio.com](https://code.visualstudio.com)
   - Install following the setup wizard

2. **Install Python Extension**

   - Open VS Code
   - Click Extensions icon (or Ctrl+Shift+X)
   - Search for "Python"
   - Install the Microsoft Python extension

3. **Create Your First Project**

   ```bash
   # Create a new folder for your Python projects
   mkdir python-learning
   cd python-learning

   # Open in VS Code
   code .
   ```

4. **Test Your Setup**
   - Create a new file: `test.py`
   - Add some code:
     ```python
     name = input("What's your name? ")
     print(f"Hello, {name}! Welcome to Python programming!")
     ```
   - Run with F5 or right-click → "Run Python File in Terminal"

#### Essential Terminal/Command Prompt Commands

```bash
# Navigate directories
cd folder_name          # Enter a folder
cd ..                   # Go back one folder
ls                      # List files (macOS/Linux)
dir                     # List files (Windows)
pwd                     # Show current directory

# Python commands
python filename.py      # Run a Python file
python -c "print('Hi')" # Run Python code directly
pip install package     # Install a Python package
pip list                # Show installed packages
```

#### Troubleshooting Common Issues

**Problem: "python is not recognized" (Windows)**

```bash
# Solution: Add Python to PATH
# 1. Search "Environment Variables" in Start menu
# 2. Click "Environment Variables"
# 3. Under "System Variables", find "Path"
# 4. Add Python installation directory (usually C:\Python3x\)
```

**Problem: Permission denied (macOS/Linux)**

```bash
# Use python3 instead of python
python3 filename.py

# Or create an alias
echo "alias python=python3" >> ~/.bashrc
source ~/.bashrc
```

**Problem: Module not found**

```bash
# Make sure you're using the right Python version
python --version
pip --version

# Install missing modules
pip install module_name
```

### What's Next?

Now that you have Python installed and your development environment set up, you're ready to dive into programming! Here's what we'll cover next:

1. **Basic Syntax** - Variables, comments, and code structure
2. **Data Types** - Numbers, strings, lists, and more
3. **Operators** - Mathematical and logical operations
4. **Input/Output** - Getting user input and displaying results

Ready to start coding? Let's move on to the [Beginner Level](#beginner-level)!

## Beginner Level

### Basic Syntax

Python's syntax is designed to be readable and straightforward. Let's start with the fundamental building blocks of Python programming.

#### Variables and Naming

Variables are containers that store data values. In Python, you don't need to declare variable types explicitly.

**Creating Variables:**

```python
# Simple variable assignment
name = "Alice"
age = 25
height = 5.6
is_student = True

# Multiple assignment
x, y, z = 1, 2, 3
a = b = c = 0  # All variables get the same value

# Printing variables
print(name)      # Output: Alice
print(age)       # Output: 25
print(height)    # Output: 5.6
print(is_student) # Output: True
```

**Variable Naming Rules:**

```python
# Valid variable names
user_name = "John"
firstName = "Jane"
age2 = 30
_private = "hidden"
PI = 3.14159

# Invalid variable names (will cause errors)
# 2age = 30        # Cannot start with number
# user-name = "X"  # Cannot contain hyphens
# class = "Math"   # Cannot use Python keywords
# user name = "Y"  # Cannot contain spaces
```

**Naming Conventions (PEP 8):**

```python
# Variables and functions: lowercase with underscores
user_name = "Alice"
total_count = 100

# Constants: uppercase with underscores
MAX_SIZE = 1000
PI = 3.14159

# Classes: PascalCase (we'll cover this later)
# class UserAccount:
#     pass
```

#### Comments and Documentation

Comments help explain your code and make it more readable. Python ignores comments when executing code.

**Single-line Comments:**

```python
# This is a single-line comment
print("Hello, World!")  # Comment at end of line

# Use comments to explain complex logic
x = 5 * 2 + 3  # Calculate: (5 * 2) + 3 = 13
```

**Multi-line Comments:**

```python
# This is a multi-line comment
# that spans several lines
# Each line needs its own # symbol

"""
This is also a multi-line comment
using triple quotes. This is actually
a string, but when not assigned to a
variable, Python ignores it.
"""

'''
You can also use single quotes
for multi-line comments.
Both work the same way.
'''
```

**Docstrings (Documentation Strings):**

```python
def calculate_area(length, width):
    """
    Calculate the area of a rectangle.

    Args:
        length (float): The length of the rectangle
        width (float): The width of the rectangle

    Returns:
        float: The area of the rectangle
    """
    return length * width

# Docstrings are used for function, class, and module documentation
# They can be accessed using the help() function
help(calculate_area)
```

#### Code Structure and Indentation

Python uses indentation to define code blocks instead of curly braces like other languages.

**Indentation Rules:**

```python
# Correct indentation
if 5 > 3:
    print("Five is greater than three")
    print("This line is also indented")

# Nested indentation
if 10 > 5:
    print("Ten is greater than five")
    if 10 > 8:
        print("Ten is also greater than eight")
    print("Back to first level")

# Function with proper indentation
def greet_user(name):
    if name:
        print(f"Hello, {name}!")
        print("Welcome to Python!")
    else:
        print("Hello, anonymous user!")

greet_user("Alice")
```

**Common Indentation Mistakes:**

```python
# Wrong: Inconsistent indentation
# if 5 > 3:
#     print("This line uses 4 spaces")
#   print("This line uses 2 spaces")  # IndentationError!

# Wrong: Missing indentation
# if 5 > 3:
# print("This should be indented")  # IndentationError!

# Correct: Consistent 4-space indentation (recommended)
if 5 > 3:
    print("This line uses 4 spaces")
    print("This line also uses 4 spaces")
```

**Best Practices for Code Structure:**

```python
# Use 4 spaces for indentation (not tabs)
# Keep lines under 79 characters when possible
# Use blank lines to separate logical sections

def main():
    # Get user input
    name = input("Enter your name: ")
    age = int(input("Enter your age: "))

    # Process the data
    if age >= 18:
        status = "adult"
    else:
        status = "minor"

    # Display results
    print(f"Name: {name}")
    print(f"Age: {age}")
    print(f"Status: {status}")

# Call the main function
if __name__ == "__main__":
    main()
```

**Python Keywords Reference:**

```python
# These are reserved words in Python - cannot be used as variable names
keywords = [
    'False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class',
    'continue', 'def', 'del', 'elif', 'else', 'except', 'finally',
    'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda',
    'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try',
    'while', 'with', 'yield'
]

# You can check if a word is a keyword
import keyword
print(keyword.iskeyword('if'))    # Output: True
print(keyword.iskeyword('hello')) # Output: False
```

**Line Continuation:**

```python
# For long lines, you can use backslash for continuation
total = 1 + 2 + 3 + 4 + 5 + \
        6 + 7 + 8 + 9 + 10

# Or use parentheses (preferred method)
total = (1 + 2 + 3 + 4 + 5 +
         6 + 7 + 8 + 9 + 10)

# Works with strings too
message = ("This is a very long message that "
           "spans multiple lines for better "
           "readability")

print(total)    # Output: 55
print(message)  # Output: This is a very long message that spans multiple lines for better readability
```

**Practice Exercise:**
Try creating a simple program that demonstrates proper syntax:

```python
# Practice: Personal Information Program
def display_info():
    """Display personal information with proper formatting."""

    # Variable assignment
    first_name = "John"
    last_name = "Doe"
    age = 28
    height = 5.9
    is_employed = True

    # Display information
    print("Personal Information:")
    print("-" * 20)  # Print a line separator
    print(f"Name: {first_name} {last_name}")
    print(f"Age: {age} years old")
    print(f"Height: {height} feet")

    # Conditional display
    if is_employed:
        print("Employment Status: Employed")
    else:
        print("Employment Status: Unemployed")

# Run the program
display_info()
```

**Expected Output:**

```
Personal Information:
--------------------
Name: John Doe
Age: 28 years old
Height: 5.9 feet
Employment Status: Employed
```

**Key Takeaways:**

- Variables don't need type declarations
- Use descriptive variable names with underscores
- Comments start with # for single lines
- Use triple quotes for multi-line comments and docstrings
- Python uses 4-space indentation to define code blocks
- Avoid using Python keywords as variable names
- Keep your code clean and well-organized

### Data Types

Python has several built-in data types that allow you to store different kinds of information. Understanding these types is crucial for effective programming.

#### Strings

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

#### Numbers

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

#### Booleans

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

#### Lists

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

#### Tuples

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

#### Dictionaries

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

#### Sets

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

**Practice Exercise - Data Types:**

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

**Key Takeaways:**

- Strings store text and have many useful methods
- Numbers include integers and floats with standard math operations
- Booleans represent True/False and are used in conditions
- Lists are mutable ordered collections
- Tuples are immutable ordered collections
- Dictionaries store key-value pairs
- Sets store unique unordered elements
- Choose the right data type for your specific needs

## Intermediate Level

### Control Structures

Control structures allow you to control the flow of your program's execution. They enable you to make decisions, repeat actions, and create more complex program logic.

#### Conditional Statements

Conditional statements allow your program to make decisions based on different conditions.

**Basic If Statements:**

```python
# Simple if statement
age = 18
if age >= 18:
    print("You are an adult")

# If-else statement
temperature = 25
if temperature > 30:
    print("It's hot outside")
else:
    print("It's not too hot")

# Multiple conditions with elif
score = 85
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
elif score >= 60:
    grade = "D"
else:
    grade = "F"

print(f"Your grade is: {grade}")
```

**Complex Conditions:**

```python
# Using logical operators in conditions
age = 25
has_license = True
has_car = True

if age >= 18 and has_license:
    if has_car:
        print("You can drive your own car")
    else:
        print("You can drive but need to borrow a car")
else:
    print("You cannot drive")

# Combining multiple conditions
weather = "sunny"
temperature = 22
if weather == "sunny" and temperature > 20:
    print("Perfect day for a picnic!")
elif weather == "rainy" or temperature < 10:
    print("Better stay inside")
else:
    print("Decent weather for outdoor activities")
```

**Nested If Statements:**

```python
# Nested if statements for complex decision making
username = "admin"
password = "secret123"
is_active = True

if username == "admin":
    if password == "secret123":
        if is_active:
            print("Welcome, Administrator!")
        else:
            print("Account is deactivated")
    else:
        print("Incorrect password")
else:
    print("Access denied")

# Same logic with combined conditions (often cleaner)
if username == "admin" and password == "secret123" and is_active:
    print("Welcome, Administrator!")
elif username == "admin" and password == "secret123":
    print("Account is deactivated")
elif username == "admin":
    print("Incorrect password")
else:
    print("Access denied")
```

**Ternary Operator (Conditional Expression):**

```python
# Ternary operator for simple conditions
age = 20
status = "adult" if age >= 18 else "minor"
print(f"Status: {status}")

# Multiple ternary operators (use sparingly)
score = 85
grade = "A" if score >= 90 else "B" if score >= 80 else "C" if score >= 70 else "F"
print(f"Grade: {grade}")

# Ternary with function calls
def get_discount(is_member):
    return 0.1 if is_member else 0.0

price = 100
is_member = True
final_price = price * (1 - get_discount(is_member))
print(f"Final price: ${final_price}")
```

#### For Loops

For loops are used to iterate over sequences (like lists, strings, ranges) or other iterable objects.

**Basic For Loops:**

```python
# Iterating over a list
fruits = ["apple", "banana", "cherry", "date"]
for fruit in fruits:
    print(f"I like {fruit}")

# Iterating over a string
word = "Python"
for letter in word:
    print(letter)

# Using range() for numeric loops
for i in range(5):
    print(f"Count: {i}")  # Output: 0, 1, 2, 3, 4

# Range with start, stop, and step
for i in range(2, 10, 2):
    print(f"Even number: {i}")  # Output: 2, 4, 6, 8
```

**Advanced For Loop Techniques:**

```python
# Using enumerate() to get index and value
colors = ["red", "green", "blue"]
for index, color in enumerate(colors):
    print(f"Color {index}: {color}")

# Starting enumerate from a different number
for index, color in enumerate(colors, start=1):
    print(f"Color {index}: {color}")

# Iterating over dictionary
person = {"name": "Alice", "age": 30, "city": "New York"}
for key, value in person.items():
    print(f"{key}: {value}")

# Iterating over multiple lists with zip()
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
cities = ["New York", "London", "Tokyo"]

for name, age, city in zip(names, ages, cities):
    print(f"{name} is {age} years old and lives in {city}")
```

**List Comprehensions:**

```python
# Traditional loop to create a list
squares = []
for i in range(10):
    squares.append(i ** 2)
print(squares)

# List comprehension (more Pythonic)
squares = [i ** 2 for i in range(10)]
print(squares)

# List comprehension with condition
even_squares = [i ** 2 for i in range(10) if i % 2 == 0]
print(even_squares)  # Output: [0, 4, 16, 36, 64]

# More complex list comprehensions
words = ["hello", "world", "python", "programming"]
lengths = [len(word) for word in words]
print(lengths)  # Output: [5, 5, 6, 11]

# Nested list comprehension
matrix = [[i * j for j in range(1, 4)] for i in range(1, 4)]
print(matrix)  # Output: [[1, 2, 3], [2, 4, 6], [3, 6, 9]]
```

#### While Loops

While loops continue executing as long as a condition remains true.

**Basic While Loops:**

```python
# Simple while loop
count = 0
while count < 5:
    print(f"Count: {count}")
    count += 1

# While loop with user input
password = ""
while password != "secret":
    password = input("Enter password: ")
    if password != "secret":
        print("Incorrect password, try again")
print("Access granted!")
```

**While Loops with Complex Conditions:**

```python
# Multiple conditions in while loop
attempts = 0
max_attempts = 3
success = False

while attempts < max_attempts and not success:
    user_input = input("Enter 'yes' to continue: ")
    if user_input.lower() == "yes":
        success = True
        print("Success!")
    else:
        attempts += 1
        print(f"Attempt {attempts} failed")

if not success:
    print("Maximum attempts reached")

# Infinite loop with break condition
while True:
    command = input("Enter command (or 'quit' to exit): ")
    if command.lower() == "quit":
        break
    print(f"You entered: {command}")
print("Goodbye!")
```

**While vs For Loops:**

```python
# When you know the number of iterations, use for
for i in range(10):
    print(i)

# When the number of iterations depends on a condition, use while
import random
number = random.randint(1, 100)
guess = 0
attempts = 0

while guess != number:
    guess = int(input("Guess the number (1-100): "))
    attempts += 1
    if guess < number:
        print("Too low!")
    elif guess > number:
        print("Too high!")

print(f"Correct! You guessed it in {attempts} attempts")
```

#### Break and Continue

`break` and `continue` statements provide additional control over loop execution.

**Using Break:**

```python
# Break exits the loop immediately
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for num in numbers:
    if num == 6:
        print("Found 6, stopping loop")
        break
    print(num)
# Output: 1, 2, 3, 4, 5, Found 6, stopping loop

# Break in while loop
count = 0
while True:
    count += 1
    if count > 5:
        break
    print(count)
print("Loop ended")

# Break in nested loops (only breaks inner loop)
for i in range(3):
    print(f"Outer loop: {i}")
    for j in range(3):
        if j == 1:
            break
        print(f"  Inner loop: {j}")
```

**Using Continue:**

```python
# Continue skips the rest of the current iteration
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for num in numbers:
    if num % 2 == 0:  # Skip even numbers
        continue
    print(f"Odd number: {num}")
# Output: Odd number: 1, Odd number: 3, Odd number: 5, etc.

# Continue in while loop
count = 0
while count < 10:
    count += 1
    if count % 3 == 0:  # Skip multiples of 3
        continue
    print(count)

# Practical example: input validation
while True:
    age = input("Enter your age (or 'quit' to exit): ")
    if age.lower() == 'quit':
        break
    
    if not age.isdigit():
        print("Please enter a valid number")
        continue
    
    age = int(age)
    if age < 0 or age > 150:
        print("Please enter a realistic age")
        continue
    
    print(f"Your age is {age}")
    break
```

#### Nested Loops

Nested loops are loops inside other loops, useful for working with multi-dimensional data.

**Basic Nested Loops:**

```python
# Simple nested loops
for i in range(3):
    for j in range(3):
        print(f"i={i}, j={j}")

# Creating a multiplication table
print("Multiplication Table:")
for i in range(1, 6):
    for j in range(1, 6):
        print(f"{i * j:2d}", end=" ")
    print()  # New line after each row

# Output:
#  1  2  3  4  5
#  2  4  6  8 10
#  3  6  9 12 15
#  4  8 12 16 20
#  5 10 15 20 25
```

**Working with 2D Lists:**

```python
# Creating and working with 2D lists
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

# Accessing elements
for row in matrix:
    for element in row:
        print(element, end=" ")
    print()

# Using indices
for i in range(len(matrix)):
    for j in range(len(matrix[i])):
        print(f"matrix[{i}][{j}] = {matrix[i][j]}")

# Finding specific elements
target = 5
found = False
for i in range(len(matrix)):
    for j in range(len(matrix[i])):
        if matrix[i][j] == target:
            print(f"Found {target} at position ({i}, {j})")
            found = True
            break
    if found:
        break
```

**Practice Exercise - Number Guessing Game:**

```python
import random

def number_guessing_game():
    """A complete number guessing game using control structures."""
    
    print("=== Number Guessing Game ===")
    print("I'm thinking of a number between 1 and 100")
    
    # Game settings
    secret_number = random.randint(1, 100)
    max_attempts = 7
    attempts = 0
    
    while attempts < max_attempts:
        try:
            # Get user input
            guess = int(input(f"Attempt {attempts + 1}/{max_attempts} - Enter your guess: "))
            attempts += 1
            
            # Check the guess
            if guess == secret_number:
                print(f"Congratulations! You guessed it in {attempts} attempts!")
                break
            elif guess < secret_number:
                print("Too low!")
            else:
                print("Too high!")
            
            # Give hints based on how close they are
            difference = abs(guess - secret_number)
            if difference <= 5:
                print("You're very close!")
            elif difference <= 15:
                print("You're getting warmer!")
            
        except ValueError:
            print("Please enter a valid number!")
            attempts -= 1  # Don't count invalid input as an attempt
            continue
    
    else:
        # This runs if the while loop completes without breaking
        print(f"Game over! The number was {secret_number}")
    
    # Ask if they want to play again
    play_again = input("Do you want to play again? (yes/no): ")
    if play_again.lower() in ['yes', 'y']:
        number_guessing_game()  # Recursive call to play again

# Run the game
number_guessing_game()
```

**Key Takeaways:**

- Use `if/elif/else` for decision making based on conditions
- `for` loops are ideal when you know the number of iterations
- `while` loops are perfect when the condition determines when to stop
- `break` exits a loop immediately, `continue` skips to the next iteration
- Nested loops are powerful for working with multi-dimensional data
- List comprehensions provide a concise way to create lists
- Always consider edge cases and input validation in real applications

## Advanced Level

### Object-Oriented Programming

**Classes and Objects:**

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def introduce(self):
        return f"Hi, I'm {self.name} and I'm {self.age} years old"

person = Person("Alice", 30)
print(person.introduce())
```

**Inheritance:**

```python
class Student(Person):
    def __init__(self, name, age, student_id):
        super().__init__(name, age)
        self.student_id = student_id
    
    def study(self, subject):
        return f"{self.name} is studying {subject}"

student = Student("Bob", 20, "S123")
print(student.introduce())
print(student.study("Python"))
```

### File Handling

**Reading and Writing Files:**

```python
# Writing to a file
with open("example.txt", "w") as file:
    file.write("Hello, World!\n")
    file.write("Python is awesome!")

# Reading from a file
with open("example.txt", "r") as file:
    content = file.read()
    print(content)

# Working with CSV files
import csv

data = [["Name", "Age"], ["Alice", 30], ["Bob", 25]]
with open("people.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerows(data)
```

## Professional Level

### Popular Libraries

**NumPy for Numerical Computing:**

```python
import numpy as np

# Creating arrays
arr = np.array([1, 2, 3, 4, 5])
matrix = np.array([[1, 2], [3, 4]])

# Mathematical operations
print(arr * 2)  # [2 4 6 8 10]
print(np.mean(arr))  # 3.0
```

**Pandas for Data Manipulation:**

```python
import pandas as pd

# Creating a DataFrame
data = {"Name": ["Alice", "Bob"], "Age": [30, 25]}
df = pd.DataFrame(data)
print(df)
```

**Requests for HTTP Operations:**

```python
import requests

response = requests.get("https://api.github.com/users/octocat")
if response.status_code == 200:
    data = response.json()
    print(data["name"])
```

### Best Practices

**PEP 8 Style Guide:**

```python
# Good: descriptive names, proper spacing
def calculate_total_price(item_price, tax_rate):
    return item_price * (1 + tax_rate)

# Good: proper imports
import os
import sys
from datetime import datetime

# Good: constants in uppercase
MAX_CONNECTIONS = 100
DEFAULT_TIMEOUT = 30
```

**Testing with unittest:**

```python
import unittest

def add_numbers(a, b):
    return a + b

class TestMathFunctions(unittest.TestCase):
    def test_add_positive_numbers(self):
        self.assertEqual(add_numbers(2, 3), 5)
    
    def test_add_negative_numbers(self):
        self.assertEqual(add_numbers(-1, -1), -2)

if __name__ == "__main__":
    unittest.main()
```

## Resources and Next Steps

### Practice Exercises

**Beginner Projects:**
1. **Calculator**: Build a command-line calculator with basic operations
2. **To-Do List**: Create a simple task management system
3. **Number Guessing Game**: Implement the game we built earlier
4. **Password Generator**: Generate secure passwords with custom criteria
5. **Unit Converter**: Convert between different units (temperature, length, weight)

**Intermediate Projects:**
1. **Contact Book**: Store and manage contact information with file persistence
2. **Expense Tracker**: Track personal expenses with categories and reporting
3. **Web Scraper**: Extract data from websites using requests and BeautifulSoup
4. **Quiz Application**: Create an interactive quiz with scoring
5. **File Organizer**: Automatically organize files by type or date

**Advanced Projects:**
1. **Web Application**: Build a Flask/Django web app with database integration
2. **Data Analysis Tool**: Analyze datasets using pandas and matplotlib
3. **API Client**: Create a client for a REST API with authentication
4. **Game Development**: Build a simple game using pygame
5. **Machine Learning Model**: Implement a basic ML model with scikit-learn

### Project Ideas

**Web Development:**
- Personal blog with Django
- E-commerce site with Flask
- REST API for mobile app
- Real-time chat application

**Data Science:**
- Stock price analysis
- Weather data visualization
- Social media sentiment analysis
- Sales forecasting model

**Automation:**
- Email automation scripts
- File backup system
- Social media posting bot
- System monitoring tools

**Desktop Applications:**
- GUI calculator with tkinter
- Image processing tool
- Database management system
- Text editor with advanced features

### External Resources

**Official Documentation:**
- [Python.org](https://python.org) - Official Python website
- [Python Documentation](https://docs.python.org/3/) - Comprehensive language reference
- [PEP 8](https://pep8.org/) - Style guide for Python code
- [Python Package Index (PyPI)](https://pypi.org/) - Repository of Python packages

**Learning Platforms:**
- [Real Python](https://realpython.com/) - In-depth tutorials and articles
- [Python.org Tutorial](https://docs.python.org/3/tutorial/) - Official tutorial
- [Automate the Boring Stuff](https://automatetheboringstuff.com/) - Practical Python programming
- [Python Crash Course](https://nostarch.com/pythoncrashcourse2e) - Comprehensive beginner book

**Practice Platforms:**
- [LeetCode](https://leetcode.com/) - Coding challenges and interview prep
- [HackerRank](https://hackerrank.com/) - Programming challenges
- [Codewars](https://codewars.com/) - Coding kata and community challenges
- [Project Euler](https://projecteuler.net/) - Mathematical programming problems

**Video Learning:**
- [Python.org Beginner's Guide](https://wiki.python.org/moin/BeginnersGuide)
- YouTube channels: Corey Schafer, Real Python, Programming with Mosh
- Online courses: Coursera, edX, Udemy

### Community and Learning Platforms

**Online Communities:**
- [r/Python](https://reddit.com/r/Python) - Python subreddit
- [Python Discord](https://pythondiscord.com/) - Active Python community
- [Stack Overflow](https://stackoverflow.com/questions/tagged/python) - Q&A platform
- [Python Forum](https://python-forum.io/) - Dedicated Python discussion forum

**Local Communities:**
- Python meetups in your city
- PyCon conferences (international and regional)
- Local programming groups and workshops
- University Python clubs and courses

### Career Paths

**Web Development:**
- Backend Developer (Django, Flask, FastAPI)
- Full-Stack Developer (Python + JavaScript)
- DevOps Engineer (automation, deployment)
- API Developer (REST, GraphQL)

**Data Science & Analytics:**
- Data Scientist (pandas, scikit-learn, TensorFlow)
- Data Analyst (pandas, matplotlib, seaborn)
- Machine Learning Engineer (ML model deployment)
- Business Intelligence Developer (data visualization)

**Software Development:**
- Software Engineer (general programming)
- Desktop Application Developer (tkinter, PyQt)
- Game Developer (pygame, Panda3D)
- Mobile App Backend Developer

**Specialized Fields:**
- Cybersecurity (penetration testing, security tools)
- Scientific Computing (research, simulations)
- Financial Technology (algorithmic trading, fintech)
- Automation Engineer (process automation, testing)

### Troubleshooting Guide

**Common Issues and Solutions:**

**Installation Problems:**
```bash
# Python not found
export PATH="/usr/local/bin/python3:$PATH"

# pip not working
python -m pip install package_name

# Virtual environment issues
python -m venv myenv
source myenv/bin/activate  # Linux/Mac
myenv\Scripts\activate     # Windows
```

**Import Errors:**
```python
# Module not found
pip install module_name

# Relative import issues
from . import module_name  # Same package
from ..package import module_name  # Parent package
```

**Performance Issues:**
```python
# Use list comprehensions instead of loops
# Good
squares = [x**2 for x in range(1000)]

# Use built-in functions
# Good
total = sum(numbers)
maximum = max(numbers)

# Profile your code
import cProfile
cProfile.run('your_function()')
```

**Debugging Tips:**
```python
# Use print statements strategically
print(f"Debug: variable = {variable}")

# Use the debugger
import pdb; pdb.set_trace()

# Use logging instead of print
import logging
logging.basicConfig(level=logging.DEBUG)
logging.debug("Debug message")
```

### Next Steps Roadmap

**Month 1-2: Master the Basics**
- Complete all beginner exercises
- Build 2-3 simple projects
- Practice daily coding (30 minutes minimum)
- Join a Python community

**Month 3-4: Intermediate Skills**
- Learn object-oriented programming thoroughly
- Work with files and data processing
- Build more complex projects
- Start contributing to open source

**Month 5-6: Specialization**
- Choose a specialization (web, data science, etc.)
- Learn relevant libraries and frameworks
- Build portfolio projects
- Network with other developers

**Month 7-12: Advanced Development**
- Master your chosen specialization
- Contribute to open source projects
- Build a strong portfolio
- Consider job applications or freelancing

**Continuous Learning:**
- Stay updated with Python releases
- Learn new libraries and tools
- Attend conferences and meetups
- Mentor other beginners
- Keep building and learning

### Final Tips for Success

1. **Practice Consistently**: Code every day, even if just for 15 minutes
2. **Build Projects**: Apply what you learn in real projects
3. **Read Code**: Study well-written Python code from open source projects
4. **Join Communities**: Connect with other Python developers
5. **Teach Others**: Explaining concepts helps solidify your understanding
6. **Stay Curious**: Always be willing to learn new things
7. **Don't Give Up**: Programming can be challenging, but persistence pays off

Remember: Becoming proficient in Python is a journey, not a destination. Keep learning, keep building, and most importantly, enjoy the process!

**Happy coding! 🐍**

---

## Quick Reference

### Python Keywords

```python
# Reserved words in Python (cannot be used as variable names)
False, None, True, and, as, assert, break, class, continue, def,
del, elif, else, except, finally, for, from, global, if, import,
in, is, lambda, nonlocal, not, or, pass, raise, return, try,
while, with, yield
```

### Common Python File Extensions

- `.py` - Python source files
- `.pyc` - Compiled Python files
- `.pyo` - Optimized compiled files
- `.pyd` - Python extension modules (Windows)
- `.so` - Python extension modules (Unix/Linux)

---

_This guide is continuously updated. Last updated: 2025_

### Operators

Operators are special symbols that perform operations on variables and values. Python supports various types of operators.

#### Arithmetic Operators

Arithmetic operators perform mathematical operations.

**Basic Arithmetic:**

```python
# Basic arithmetic operations
a = 10
b = 3

print(a + b)   # Addition: 13
print(a - b)   # Subtraction: 7
print(a * b)   # Multiplication: 30
print(a / b)   # Division: 3.3333333333333335
print(a // b)  # Floor division: 3
print(a % b)   # Modulus (remainder): 1
print(a ** b)  # Exponentiation: 1000
```

**Operator Precedence:**

```python
# Order of operations (PEMDAS/BODMAS)
result = 2 + 3 * 4      # Multiplication first: 2 + 12 = 14
print(result)           # Output: 14

result = (2 + 3) * 4    # Parentheses first: 5 * 4 = 20
print(result)           # Output: 20

result = 2 ** 3 ** 2    # Exponentiation is right-associative: 2 ** (3 ** 2) = 2 ** 9 = 512
print(result)           # Output: 512

# Complex expression
result = 10 + 5 * 2 - 3 / 2 + 4 ** 2
# Step by step: 10 + 10 - 1.5 + 16 = 34.5
print(result)           # Output: 34.5
```

**Working with Different Number Types:**

```python
# Integer and float operations
int_num = 10
float_num = 3.5

print(int_num + float_num)    # Output: 13.5 (result is float)
print(int_num * float_num)    # Output: 35.0 (result is float)
print(int_num / 2)            # Output: 5.0 (division always returns float)
print(int_num // 3)           # Output: 3 (floor division with integers)
print(float_num // 2)         # Output: 1.0 (floor division with floats)
```

#### Comparison Operators

Comparison operators compare values and return boolean results.

**Basic Comparisons:**

```python
x = 10
y = 5

print(x == y)   # Equal to: False
print(x != y)   # Not equal to: True
print(x > y)    # Greater than: True
print(x < y)    # Less than: False
print(x >= y)   # Greater than or equal to: True
print(x <= y)   # Less than or equal to: False
```

**Comparing Different Data Types:**

```python
# String comparisons (lexicographic order)
print("apple" < "banana")     # Output: True
print("Apple" < "apple")      # Output: True (uppercase comes first)
print("10" < "2")             # Output: True (string comparison, not numeric)

# Numeric comparisons
print(10 == 10.0)             # Output: True (values are equal)
print(10 is 10.0)             # Output: False (different types)

# List comparisons
print([1, 2, 3] == [1, 2, 3]) # Output: True
print([1, 2] < [1, 2, 3])     # Output: True (shorter list is "less")
```

**Chaining Comparisons:**

```python
# You can chain comparison operators
age = 25
print(18 <= age <= 65)        # Output: True (equivalent to: 18 <= age and age <= 65)

score = 85
print(80 <= score < 90)       # Output: True

# Multiple chaining
x = 5
print(1 < x < 10 < 20)        # Output: True
```

#### Logical Operators

Logical operators combine boolean values or expressions.

**Basic Logical Operations:**

```python
# Basic logical operators
a = True
b = False

print(a and b)    # Output: False (both must be True)
print(a or b)     # Output: True (at least one must be True)
print(not a)      # Output: False (opposite of a)
print(not b)      # Output: True (opposite of b)
```

**Logical Operators with Expressions:**

```python
age = 25
has_license = True
has_car = False

# Complex logical expressions
can_drive = age >= 18 and has_license
print(f"Can drive: {can_drive}")  # Output: Can drive: True

can_drive_alone = age >= 18 and has_license and has_car
print(f"Can drive alone: {can_drive_alone}")  # Output: Can drive alone: False

needs_ride = not has_car or not has_license
print(f"Needs ride: {needs_ride}")  # Output: Needs ride: True
```

**Short-Circuit Evaluation:**

```python
# Logical operators use short-circuit evaluation
def expensive_function():
    print("This function was called!")
    return True

# In 'and' operations, if first is False, second isn't evaluated
result = False and expensive_function()  # expensive_function() is NOT called
print(result)  # Output: False

# In 'or' operations, if first is True, second isn't evaluated
result = True or expensive_function()   # expensive_function() is NOT called
print(result)  # Output: True
```

#### Assignment Operators

Assignment operators assign values to variables and can combine assignment with arithmetic operations.

**Basic Assignment:**

```python
# Basic assignment
x = 10
y = x
print(f"x = {x}, y = {y}")  # Output: x = 10, y = 10
```

**Compound Assignment Operators:**

```python
# Compound assignment operators
x = 10

x += 5    # Equivalent to: x = x + 5
print(x)  # Output: 15

x -= 3    # Equivalent to: x = x - 3
print(x)  # Output: 12

x *= 2    # Equivalent to: x = x * 2
print(x)  # Output: 24

x /= 4    # Equivalent to: x = x / 4
print(x)  # Output: 6.0

x //= 2   # Equivalent to: x = x // 2
print(x)  # Output: 3.0

x %= 2    # Equivalent to: x = x % 2
print(x)  # Output: 1.0

x **= 3   # Equivalent to: x = x ** 3
print(x)  # Output: 1.0
```

**Assignment with Other Data Types:**

```python
# String compound assignment
message = "Hello"
message += " World"
print(message)  # Output: Hello World

# List compound assignment
numbers = [1, 2, 3]
numbers += [4, 5]
print(numbers)  # Output: [1, 2, 3, 4, 5]

# Multiple assignment
a, b, c = 1, 2, 3
print(f"a={a}, b={b}, c={c}")  # Output: a=1, b=2, c=3

# Swapping variables
a, b = b, a
print(f"a={a}, b={b}")  # Output: a=2, b=1
```

### Input and Output

Interacting with users through input and output is fundamental to most programs.

#### Getting User Input

The `input()` function allows you to get text input from users.

**Basic Input:**

```python
# Getting user input
name = input("What's your name? ")
print(f"Hello, {name}!")

# Input always returns a string
age_str = input("How old are you? ")
print(f"You entered: {age_str} (type: {type(age_str)})")
```

**Converting Input Types:**

```python
# Converting string input to numbers
age = int(input("Enter your age: "))
height = float(input("Enter your height in feet: "))

print(f"Age: {age} (type: {type(age)})")
print(f"Height: {height} (type: {type(height)})")

# Calculating with converted input
birth_year = 2024 - age
print(f"You were born around {birth_year}")
```

**Handling Input Errors:**

```python
# Basic error handling for input
try:
    number = int(input("Enter a number: "))
    print(f"You entered: {number}")
except ValueError:
    print("That's not a valid number!")

# More robust input handling
def get_integer(prompt):
    while True:
        try:
            return int(input(prompt))
        except ValueError:
            print("Please enter a valid integer.")

age = get_integer("Enter your age: ")
print(f"Your age is {age}")
```

**Multiple Inputs:**

```python
# Getting multiple values in one line
data = input("Enter your name, age, and city (separated by commas): ")
name, age, city = data.split(", ")
print(f"Name: {name}, Age: {age}, City: {city}")

# Getting multiple numbers
numbers_str = input("Enter numbers separated by spaces: ")
numbers = [int(x) for x in numbers_str.split()]
print(f"Numbers: {numbers}")
print(f"Sum: {sum(numbers)}")
```

#### Printing Output

The `print()` function is used to display output to the user.

**Basic Printing:**

```python
# Basic print statements
print("Hello, World!")
print("Python", "is", "awesome")  # Multiple arguments
print("Line 1")
print("Line 2")
```

**Print Function Parameters:**

```python
# sep parameter (separator between arguments)
print("apple", "banana", "cherry", sep=", ")  # Output: apple, banana, cherry
print("2024", "12", "25", sep="-")            # Output: 2024-12-25

# end parameter (what to print at the end)
print("Hello", end=" ")
print("World")  # Output: Hello World (on same line)

print("Loading", end="")
for i in range(3):
    print(".", end="")
print(" Done!")  # Output: Loading... Done!
```

**Formatting Output:**

```python
name = "Alice"
age = 30
salary = 75000.50

# f-strings (recommended for Python 3.6+)
print(f"Name: {name}")
print(f"Age: {age}")
print(f"Salary: ${salary:,.2f}")  # Output: Salary: $75,000.50

# .format() method
print("Name: {}, Age: {}".format(name, age))
print("Salary: ${:,.2f}".format(salary))

# % formatting (older style)
print("Name: %s, Age: %d" % (name, age))
```

**Advanced Formatting:**

```python
# Number formatting
pi = 3.14159265359
print(f"Pi: {pi:.2f}")        # Output: Pi: 3.14
print(f"Pi: {pi:.4f}")        # Output: Pi: 3.1416

# Percentage formatting
score = 0.875
print(f"Score: {score:.1%}")  # Output: Score: 87.5%

# Padding and alignment
print(f"{'Name':<10} {'Age':>5} {'City':^15}")
print(f"{'Alice':<10} {25:>5} {'New York':^15}")
print(f"{'Bob':<10} {30:>5} {'Chicago':^15}")

# Output:
# Name            Age      City
# Alice            25    New York
# Bob              30     Chicago
```

**Printing Data Structures:**

```python
# Printing lists, dictionaries, etc.
numbers = [1, 2, 3, 4, 5]
person = {"name": "Alice", "age": 30, "city": "New York"}

print("Numbers:", numbers)
print("Person:", person)

# Pretty printing for better readability
import pprint
complex_data = {
    "users": [
        {"name": "Alice", "age": 30, "hobbies": ["reading", "swimming"]},
        {"name": "Bob", "age": 25, "hobbies": ["gaming", "cooking"]}
    ]
}

print("Regular print:")
print(complex_data)

print("\nPretty print:")
pprint.pprint(complex_data)
```

**Practice Exercise - Calculator:**

```python
def simple_calculator():
    """A simple calculator using input/output and operators."""
    
    print("=== Simple Calculator ===")
    print("Available operations: +, -, *, /, //, %, **")
    
    try:
        # Get input from user
        num1 = float(input("Enter first number: "))
        operator = input("Enter operator (+, -, *, /, //, %, **): ")
        num2 = float(input("Enter second number: "))
        
        # Perform calculation based on operator
        if operator == "+":
            result = num1 + num2
        elif operator == "-":
            result = num1 - num2
        elif operator == "*":
            result = num1 * num2
        elif operator == "/":
            if num2 != 0:
                result = num1 / num2
            else:
                print("Error: Division by zero!")
                return
        elif operator == "//":
            if num2 != 0:
                result = num1 // num2
            else:
                print("Error: Division by zero!")
                return
        elif operator == "%":
            if num2 != 0:
                result = num1 % num2
            else:
                print("Error: Division by zero!")
                return
        elif operator == "**":
            result = num1 ** num2
        else:
            print("Error: Invalid operator!")
            return
        
        # Display result
        print(f"\nResult: {num1} {operator} {num2} = {result}")
        
        # Additional information
        print(f"Result type: {type(result)}")
        if isinstance(result, float) and result.is_integer():
            print(f"As integer: {int(result)}")
            
    except ValueError:
        print("Error: Please enter valid numbers!")
    except Exception as e:
        print(f"An error occurred: {e}")

# Run the calculator
simple_calculator()
```

**Key Takeaways:**

- Arithmetic operators perform mathematical calculations with proper precedence
- Comparison operators return boolean values and can be chained
- Logical operators combine boolean expressions with short-circuit evaluation
- Assignment operators can combine assignment with arithmetic operations
- `input()` always returns strings that need conversion for numeric operations
- `print()` has many formatting options for professional output
- Always handle potential input errors in real applications
- Use f-strings for modern, readable string formatting#
## Functions

Functions are reusable blocks of code that perform specific tasks. They help organize code, reduce repetition, and make programs more modular.

#### Function Definition

**Basic Function Syntax:**

```python
# Simple function definition
def greet():
    print("Hello, World!")

# Call the function
greet()  # Output: Hello, World!

# Function with parameters
def greet_person(name):
    print(f"Hello, {name}!")

greet_person("Alice")  # Output: Hello, Alice!

# Function with multiple parameters
def add_numbers(a, b):
    result = a + b
    print(f"{a} + {b} = {result}")

add_numbers(5, 3)  # Output: 5 + 3 = 8
```

#### Parameters and Arguments

**Different Types of Parameters:**

```python
# Positional parameters
def introduce(name, age, city):
    print(f"My name is {name}, I'm {age} years old, and I live in {city}")

introduce("Alice", 25, "New York")

# Default parameters
def greet_with_title(name, title="Mr./Ms."):
    print(f"Hello, {title} {name}")

greet_with_title("Smith")           # Output: Hello, Mr./Ms. Smith
greet_with_title("Smith", "Dr.")    # Output: Hello, Dr. Smith

# Keyword arguments
def create_profile(name, age, city="Unknown", occupation="Student"):
    print(f"Name: {name}")
    print(f"Age: {age}")
    print(f"City: {city}")
    print(f"Occupation: {occupation}")

create_profile("Bob", 30, occupation="Engineer", city="Chicago")
```

**Variable-Length Arguments:**

```python
# *args for variable positional arguments
def sum_all(*numbers):
    total = 0
    for num in numbers:
        total += num
    return total

print(sum_all(1, 2, 3))        # Output: 6
print(sum_all(1, 2, 3, 4, 5))  # Output: 15

# **kwargs for variable keyword arguments
def print_info(**info):
    for key, value in info.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=25, city="New York")

# Combining all parameter types
def complex_function(required, default="default", *args, **kwargs):
    print(f"Required: {required}")
    print(f"Default: {default}")
    print(f"Args: {args}")
    print(f"Kwargs: {kwargs}")

complex_function("test", "custom", 1, 2, 3, name="Alice", age=25)
```

#### Return Values

**Basic Return Statements:**

```python
# Function that returns a value
def square(number):
    return number ** 2

result = square(5)
print(result)  # Output: 25

# Function with conditional returns
def absolute_value(number):
    if number >= 0:
        return number
    else:
        return -number

print(absolute_value(-5))  # Output: 5
print(absolute_value(3))   # Output: 3

# Multiple return values
def get_name_parts(full_name):
    parts = full_name.split()
    first_name = parts[0]
    last_name = parts[-1]
    return first_name, last_name

first, last = get_name_parts("John Doe Smith")
print(f"First: {first}, Last: {last}")  # Output: First: John, Last: Smith
```

**Early Returns and Guard Clauses:**

```python
# Using early returns for cleaner code
def calculate_discount(price, customer_type):
    # Guard clauses
    if price <= 0:
        return 0
    
    if customer_type == "premium":
        return price * 0.2
    elif customer_type == "regular":
        return price * 0.1
    else:
        return 0

# Function with validation
def divide_numbers(a, b):
    if b == 0:
        return None, "Cannot divide by zero"
    
    result = a / b
    return result, "Success"

quotient, message = divide_numbers(10, 2)
print(f"Result: {quotient}, Message: {message}")
```

#### Variable Scope

**Local vs Global Scope:**

```python
# Global variable
global_var = "I'm global"

def test_scope():
    # Local variable
    local_var = "I'm local"
    print(f"Inside function: {global_var}")
    print(f"Inside function: {local_var}")

test_scope()
print(f"Outside function: {global_var}")
# print(local_var)  # This would cause an error

# Modifying global variables
counter = 0

def increment():
    global counter
    counter += 1

print(f"Counter: {counter}")  # Output: 0
increment()
print(f"Counter: {counter}")  # Output: 1

# Nonlocal scope (nested functions)
def outer_function():
    x = 10
    
    def inner_function():
        nonlocal x
        x += 5
        print(f"Inner x: {x}")
    
    inner_function()
    print(f"Outer x: {x}")

outer_function()
```

#### Lambda Functions

**Basic Lambda Functions:**

```python
# Regular function
def square(x):
    return x ** 2

# Equivalent lambda function
square_lambda = lambda x: x ** 2

print(square(5))        # Output: 25
print(square_lambda(5)) # Output: 25

# Lambda with multiple parameters
add = lambda x, y: x + y
print(add(3, 4))  # Output: 7

# Using lambda with built-in functions
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x ** 2, numbers))
print(squared)  # Output: [1, 4, 9, 16, 25]

# Filtering with lambda
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(even_numbers)  # Output: [2, 4]

# Sorting with lambda
students = [("Alice", 85), ("Bob", 90), ("Charlie", 78)]
students.sort(key=lambda student: student[1])  # Sort by grade
print(students)  # Output: [('Charlie', 78), ('Alice', 85), ('Bob', 90)]
```

#### Function Documentation

**Docstrings and Documentation:**

```python
def calculate_area(length, width):
    """
    Calculate the area of a rectangle.
    
    Args:
        length (float): The length of the rectangle
        width (float): The width of the rectangle
    
    Returns:
        float: The area of the rectangle
    
    Raises:
        ValueError: If length or width is negative
    
    Example:
        >>> calculate_area(5, 3)
        15.0
    """
    if length < 0 or width < 0:
        raise ValueError("Length and width must be non-negative")
    
    return length * width

# Accessing docstring
print(calculate_area.__doc__)
help(calculate_area)

# Type hints (Python 3.5+)
def greet_user(name: str, age: int) -> str:
    """Greet a user with their name and age."""
    return f"Hello {name}, you are {age} years old"

# Function annotations
def process_data(data: list, multiplier: float = 1.0) -> list:
    """Process data by multiplying each element."""
    return [item * multiplier for item in data]
```

**Practice Exercise - Advanced Calculator:**

```python
def advanced_calculator():
    """An advanced calculator with multiple functions."""
    
    def add(x, y):
        """Add two numbers."""
        return x + y
    
    def subtract(x, y):
        """Subtract y from x."""
        return x - y
    
    def multiply(x, y):
        """Multiply two numbers."""
        return x * y
    
    def divide(x, y):
        """Divide x by y."""
        if y == 0:
            return None, "Cannot divide by zero"
        return x / y, "Success"
    
    def power(x, y):
        """Raise x to the power of y."""
        return x ** y
    
    def factorial(n):
        """Calculate factorial of n."""
        if n < 0:
            return None, "Factorial not defined for negative numbers"
        if n == 0 or n == 1:
            return 1, "Success"
        
        result = 1
        for i in range(2, n + 1):
            result *= i
        return result, "Success"
    
    # Dictionary of operations
    operations = {
        '+': add,
        '-': subtract,
        '*': multiply,
        '/': divide,
        '**': power,
        '!': lambda x: factorial(int(x))
    }
    
    print("=== Advanced Calculator ===")
    print("Available operations: +, -, *, /, **, ! (factorial)")
    
    while True:
        try:
            operation = input("\nEnter operation (or 'quit' to exit): ").strip()
            
            if operation.lower() == 'quit':
                break
            
            if operation == '!':
                num = float(input("Enter number for factorial: "))
                result, message = operations[operation](num)
                if result is not None:
                    print(f"{int(num)}! = {result}")
                else:
                    print(f"Error: {message}")
            
            elif operation in operations:
                num1 = float(input("Enter first number: "))
                num2 = float(input("Enter second number: "))
                
                if operation == '/':
                    result, message = operations[operation](num1, num2)
                    if result is not None:
                        print(f"{num1} {operation} {num2} = {result}")
                    else:
                        print(f"Error: {message}")
                else:
                    result = operations[operation](num1, num2)
                    print(f"{num1} {operation} {num2} = {result}")
            
            else:
                print("Invalid operation!")
        
        except ValueError:
            print("Please enter valid numbers!")
        except Exception as e:
            print(f"An error occurred: {e}")
    
    print("Calculator closed. Goodbye!")

# Run the calculator
advanced_calculator()
```

**Key Takeaways:**

- Functions make code reusable and organized
- Use parameters to make functions flexible
- Return values to get results from functions
- Understand scope: local, global, and nonlocal
- Lambda functions are useful for short, simple operations
- Document functions with docstrings and type hints
- Functions can be stored in variables and passed as arguments
- Use default parameters to make functions more flexible### Er
ror Handling

Error handling allows your programs to gracefully handle unexpected situations and continue running or fail gracefully.

#### Try/Except Blocks

**Basic Exception Handling:**

```python
# Basic try/except
try:
    number = int(input("Enter a number: "))
    result = 10 / number
    print(f"Result: {result}")
except ValueError:
    print("That's not a valid number!")
except ZeroDivisionError:
    print("Cannot divide by zero!")

# Catching multiple exceptions
try:
    data = [1, 2, 3]
    index = int(input("Enter index: "))
    print(data[index])
except (ValueError, IndexError) as e:
    print(f"Error: {e}")

# Generic exception handling
try:
    risky_operation()
except Exception as e:
    print(f"An unexpected error occurred: {e}")
```

#### Common Exception Types

**Built-in Exception Types:**

```python
# ValueError - inappropriate value
try:
    age = int("not a number")
except ValueError as e:
    print(f"ValueError: {e}")

# TypeError - inappropriate type
try:
    result = "hello" + 5
except TypeError as e:
    print(f"TypeError: {e}")

# IndexError - list index out of range
try:
    numbers = [1, 2, 3]
    print(numbers[10])
except IndexError as e:
    print(f"IndexError: {e}")

# KeyError - dictionary key not found
try:
    person = {"name": "Alice"}
    print(person["age"])
except KeyError as e:
    print(f"KeyError: {e}")

# FileNotFoundError - file doesn't exist
try:
    with open("nonexistent.txt", "r") as file:
        content = file.read()
except FileNotFoundError as e:
    print(f"FileNotFoundError: {e}")
```

#### Finally Blocks

**Using Finally for Cleanup:**

```python
# Finally block always executes
def read_file(filename):
    file = None
    try:
        file = open(filename, 'r')
        content = file.read()
        return content
    except FileNotFoundError:
        print(f"File {filename} not found")
        return None
    except Exception as e:
        print(f"Error reading file: {e}")
        return None
    finally:
        if file:
            file.close()
            print("File closed")

# Using context managers (preferred for files)
def read_file_better(filename):
    try:
        with open(filename, 'r') as file:
            return file.read()
    except FileNotFoundError:
        print(f"File {filename} not found")
        return None
```

#### Custom Exceptions

**Creating Custom Exception Classes:**

```python
# Custom exception classes
class InvalidAgeError(Exception):
    """Raised when age is invalid"""
    def __init__(self, age, message="Age must be between 0 and 150"):
        self.age = age
        self.message = message
        super().__init__(self.message)

class BankAccountError(Exception):
    """Base class for bank account errors"""
    pass

class InsufficientFundsError(BankAccountError):
    """Raised when account has insufficient funds"""
    def __init__(self, balance, amount):
        self.balance = balance
        self.amount = amount
        message = f"Insufficient funds: ${balance} available, ${amount} requested"
        super().__init__(message)

# Using custom exceptions
def validate_age(age):
    if not isinstance(age, int):
        raise TypeError("Age must be an integer")
    if age < 0 or age > 150:
        raise InvalidAgeError(age)
    return True

def withdraw_money(balance, amount):
    if amount > balance:
        raise InsufficientFundsError(balance, amount)
    return balance - amount

# Example usage
try:
    validate_age(-5)
except InvalidAgeError as e:
    print(f"Age validation error: {e}")

try:
    new_balance = withdraw_money(100, 150)
except InsufficientFundsError as e:
    print(f"Transaction failed: {e}")
```

#### Debugging Techniques

**Debugging Strategies:**

```python
import traceback
import logging

# Using print statements for debugging
def calculate_average(numbers):
    print(f"Debug: Input numbers = {numbers}")  # Debug print
    
    if not numbers:
        print("Debug: Empty list provided")  # Debug print
        return 0
    
    total = sum(numbers)
    count = len(numbers)
    average = total / count
    
    print(f"Debug: total={total}, count={count}, average={average}")  # Debug print
    return average

# Using logging for better debugging
logging.basicConfig(level=logging.DEBUG, format='%(levelname)s: %(message)s')

def process_data(data):
    logging.debug(f"Processing data: {data}")
    
    try:
        result = [x * 2 for x in data]
        logging.info(f"Successfully processed {len(data)} items")
        return result
    except TypeError as e:
        logging.error(f"Type error in process_data: {e}")
        return []

# Exception information and traceback
def divide_with_debug(a, b):
    try:
        return a / b
    except Exception as e:
        print(f"Exception type: {type(e).__name__}")
        print(f"Exception message: {str(e)}")
        print("Full traceback:")
        traceback.print_exc()
        return None

# Assert statements for debugging
def calculate_factorial(n):
    assert isinstance(n, int), "n must be an integer"
    assert n >= 0, "n must be non-negative"
    
    if n <= 1:
        return 1
    return n * calculate_factorial(n - 1)

# Example usage
try:
    result = calculate_factorial(-5)
except AssertionError as e:
    print(f"Assertion failed: {e}")
```

**Practice Exercise - Robust File Processor:**

```python
import os
import json
import csv
from datetime import datetime

class FileProcessorError(Exception):
    """Base exception for file processor"""
    pass

class UnsupportedFileTypeError(FileProcessorError):
    """Raised when file type is not supported"""
    pass

class FileProcessor:
    """A robust file processor with comprehensive error handling."""
    
    def __init__(self):
        self.supported_extensions = ['.txt', '.json', '.csv']
        self.log_file = 'processor.log'
    
    def log_error(self, message):
        """Log errors to file with timestamp."""
        try:
            with open(self.log_file, 'a') as log:
                timestamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
                log.write(f"[{timestamp}] ERROR: {message}\n")
        except Exception as e:
            print(f"Failed to write to log file: {e}")
    
    def validate_file(self, filepath):
        """Validate file exists and is supported."""
        if not os.path.exists(filepath):
            raise FileNotFoundError(f"File not found: {filepath}")
        
        _, ext = os.path.splitext(filepath)
        if ext.lower() not in self.supported_extensions:
            raise UnsupportedFileTypeError(f"Unsupported file type: {ext}")
        
        return True
    
    def read_text_file(self, filepath):
        """Read a text file safely."""
        try:
            with open(filepath, 'r', encoding='utf-8') as file:
                return file.read()
        except UnicodeDecodeError:
            # Try different encoding
            with open(filepath, 'r', encoding='latin-1') as file:
                return file.read()
    
    def read_json_file(self, filepath):
        """Read a JSON file safely."""
        with open(filepath, 'r') as file:
            return json.load(file)
    
    def read_csv_file(self, filepath):
        """Read a CSV file safely."""
        data = []
        with open(filepath, 'r') as file:
            reader = csv.DictReader(file)
            for row in reader:
                data.append(row)
        return data
    
    def process_file(self, filepath):
        """Process a file based on its type."""
        try:
            # Validate file
            self.validate_file(filepath)
            
            # Get file extension
            _, ext = os.path.splitext(filepath)
            ext = ext.lower()
            
            print(f"Processing {filepath}...")
            
            # Process based on file type
            if ext == '.txt':
                content = self.read_text_file(filepath)
                return {
                    'type': 'text',
                    'content': content,
                    'word_count': len(content.split()),
                    'char_count': len(content)
                }
            
            elif ext == '.json':
                content = self.read_json_file(filepath)
                return {
                    'type': 'json',
                    'content': content,
                    'keys': list(content.keys()) if isinstance(content, dict) else None
                }
            
            elif ext == '.csv':
                content = self.read_csv_file(filepath)
                return {
                    'type': 'csv',
                    'content': content,
                    'row_count': len(content),
                    'columns': list(content[0].keys()) if content else []
                }
        
        except FileNotFoundError as e:
            error_msg = f"File not found: {e}"
            self.log_error(error_msg)
            print(error_msg)
            return None
        
        except UnsupportedFileTypeError as e:
            error_msg = f"Unsupported file type: {e}"
            self.log_error(error_msg)
            print(error_msg)
            return None
        
        except json.JSONDecodeError as e:
            error_msg = f"Invalid JSON format in {filepath}: {e}"
            self.log_error(error_msg)
            print(error_msg)
            return None
        
        except csv.Error as e:
            error_msg = f"CSV processing error in {filepath}: {e}"
            self.log_error(error_msg)
            print(error_msg)
            return None
        
        except PermissionError as e:
            error_msg = f"Permission denied accessing {filepath}: {e}"
            self.log_error(error_msg)
            print(error_msg)
            return None
        
        except Exception as e:
            error_msg = f"Unexpected error processing {filepath}: {e}"
            self.log_error(error_msg)
            print(error_msg)
            return None
    
    def process_multiple_files(self, filepaths):
        """Process multiple files and return results."""
        results = {}
        
        for filepath in filepaths:
            try:
                result = self.process_file(filepath)
                results[filepath] = result
            except Exception as e:
                results[filepath] = f"Error: {e}"
        
        return results

# Example usage
def main():
    processor = FileProcessor()
    
    # Test files (create some sample files for testing)
    test_files = ['sample.txt', 'data.json', 'info.csv', 'nonexistent.txt']
    
    print("=== File Processor Demo ===")
    
    for filepath in test_files:
        print(f"\n--- Processing {filepath} ---")
        result = processor.process_file(filepath)
        
        if result:
            print(f"Success! File type: {result['type']}")
            if result['type'] == 'text':
                print(f"Word count: {result['word_count']}")
            elif result['type'] == 'csv':
                print(f"Rows: {result['row_count']}")
        else:
            print("Processing failed - check log file for details")

if __name__ == "__main__":
    main()
```

**Key Takeaways:**

- Use try/except blocks to handle specific exceptions
- Always handle the most specific exceptions first
- Use finally blocks for cleanup operations
- Create custom exceptions for domain-specific errors
- Log errors for debugging and monitoring
- Use assert statements for debugging assumptions
- Handle exceptions at the appropriate level in your code
- Don't catch exceptions you can't handle meaningfully

### Modules and Packages

Modules and packages help organize code into reusable components and manage larger Python projects effectively.

#### Importing Modules

**Basic Import Statements:**

```python
# Import entire module
import math
print(math.pi)        # Output: 3.141592653589793
print(math.sqrt(16))  # Output: 4.0

# Import specific functions
from math import pi, sqrt, cos
print(pi)        # Output: 3.141592653589793
print(sqrt(25))  # Output: 5.0
print(cos(0))    # Output: 1.0

# Import with alias
import datetime as dt
now = dt.datetime.now()
print(now)

# Import all (use sparingly)
from math import *
print(sin(pi/2))  # Output: 1.0
```

**Different Import Methods:**

```python
# Standard library modules
import os
import sys
import random
import json
from datetime import datetime, timedelta
from collections import defaultdict, Counter

# Using imported modules
print(f"Current directory: {os.getcwd()}")
print(f"Python version: {sys.version}")
print(f"Random number: {random.randint(1, 100)}")

# JSON operations
data = {"name": "Alice", "age": 30}
json_string = json.dumps(data)
print(f"JSON: {json_string}")

# Date operations
today = datetime.now()
tomorrow = today + timedelta(days=1)
print(f"Tomorrow: {tomorrow.strftime('%Y-%m-%d')}")
```

#### Creating Custom Modules

**Creating Your First Module:**

Create a file called `my_math.py`:

```python
# my_math.py - Custom math utilities module
"""
A custom math utilities module.
Provides additional mathematical functions.
"""

PI = 3.14159265359

def circle_area(radius):
    """Calculate the area of a circle."""
    return PI * radius ** 2

def circle_circumference(radius):
    """Calculate the circumference of a circle."""
    return 2 * PI * radius

def rectangle_area(length, width):
    """Calculate the area of a rectangle."""
    return length * width

def is_prime(n):
    """Check if a number is prime."""
    if n < 2:
        return False
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True

def factorial(n):
    """Calculate factorial of n."""
    if n <= 1:
        return 1
    return n * factorial(n - 1)

# Module-level code (runs when imported)
print(f"my_math module loaded. PI = {PI}")

# This runs only when the module is executed directly
if __name__ == "__main__":
    print("Testing my_math module:")
    print(f"Circle area (radius=5): {circle_area(5)}")
    print(f"Is 17 prime? {is_prime(17)}")
    print(f"Factorial of 5: {factorial(5)}")
```

**Using Your Custom Module:**

```python
# Using the custom module
import my_math

# Use functions from the module
area = my_math.circle_area(10)
print(f"Circle area: {area}")

# Import specific functions
from my_math import is_prime, factorial

print(f"Is 29 prime? {is_prime(29)}")
print(f"5! = {factorial(5)}")

# Access module attributes
print(f"PI from my_math: {my_math.PI}")
```

#### Package Structure

**Creating a Package:**

Create the following directory structure:

```
my_package/
    __init__.py
    math_utils.py
    string_utils.py
    file_utils.py
    subpackage/
        __init__.py
        advanced_math.py
```

**my_package/__init__.py:**

```python
# my_package/__init__.py
"""
My custom package for various utilities.
"""

# Package version
__version__ = "1.0.0"

# Import key functions to package level
from .math_utils import circle_area, is_prime
from .string_utils import reverse_string, count_words

# Package-level variables
PACKAGE_NAME = "my_package"

print(f"{PACKAGE_NAME} v{__version__} loaded")
```

**my_package/math_utils.py:**

```python
# my_package/math_utils.py
"""Math utility functions."""

import math

def circle_area(radius):
    """Calculate circle area."""
    return math.pi * radius ** 2

def is_prime(n):
    """Check if number is prime."""
    if n < 2:
        return False
    for i in range(2, int(math.sqrt(n)) + 1):
        if n % i == 0:
            return False
    return True

def gcd(a, b):
    """Calculate greatest common divisor."""
    while b:
        a, b = b, a % b
    return a
```

**my_package/string_utils.py:**

```python
# my_package/string_utils.py
"""String utility functions."""

def reverse_string(s):
    """Reverse a string."""
    return s[::-1]

def count_words(text):
    """Count words in text."""
    return len(text.split())

def capitalize_words(text):
    """Capitalize each word."""
    return ' '.join(word.capitalize() for word in text.split())

def remove_duplicates(text):
    """Remove duplicate characters."""
    return ''.join(dict.fromkeys(text))
```

**Using Your Package:**

```python
# Import entire package
import my_package

# Use functions imported at package level
area = my_package.circle_area(5)
print(f"Area: {area}")

# Import specific modules
from my_package import string_utils

reversed_text = string_utils.reverse_string("Hello")
print(f"Reversed: {reversed_text}")

# Import specific functions
from my_package.math_utils import gcd
print(f"GCD of 48 and 18: {gcd(48, 18)}")
```

#### Standard Library Overview

**Essential Standard Library Modules:**

```python
# os - Operating system interface
import os
print(f"Current directory: {os.getcwd()}")
print(f"Files in current directory: {os.listdir('.')}")

# sys - System-specific parameters
import sys
print(f"Python path: {sys.path[0]}")
print(f"Command line arguments: {sys.argv}")

# datetime - Date and time handling
from datetime import datetime, date, timedelta
now = datetime.now()
print(f"Current time: {now}")
print(f"Date only: {now.date()}")
print(f"Time only: {now.time()}")

# random - Generate random numbers
import random
print(f"Random integer: {random.randint(1, 100)}")
print(f"Random choice: {random.choice(['apple', 'banana', 'cherry'])}")
numbers = [1, 2, 3, 4, 5]
random.shuffle(numbers)
print(f"Shuffled: {numbers}")

# collections - Specialized container datatypes
from collections import Counter, defaultdict, deque

# Counter for counting
text = "hello world"
letter_count = Counter(text)
print(f"Letter frequencies: {letter_count}")

# defaultdict for default values
dd = defaultdict(list)
dd['fruits'].append('apple')
dd['fruits'].append('banana')
print(f"Default dict: {dict(dd)}")

# itertools - Iterator functions
import itertools

# Combinations and permutations
colors = ['red', 'green', 'blue']
combinations = list(itertools.combinations(colors, 2))
print(f"Combinations: {combinations}")

# pathlib - Object-oriented filesystem paths
from pathlib import Path

current_file = Path(__file__)
print(f"Current file: {current_file.name}")
print(f"Parent directory: {current_file.parent}")
print(f"File exists: {current_file.exists()}")
```

#### Virtual Environments

**Creating and Using Virtual Environments:**

```bash
# Create a virtual environment
python -m venv myproject_env

# Activate virtual environment
# On Windows:
myproject_env\Scripts\activate

# On macOS/Linux:
source myproject_env/bin/activate

# Install packages in virtual environment
pip install requests pandas numpy

# List installed packages
pip list

# Save requirements
pip freeze > requirements.txt

# Install from requirements
pip install -r requirements.txt

# Deactivate virtual environment
deactivate
```

**Managing Dependencies:**

Create a `requirements.txt` file:

```txt
requests==2.28.1
pandas==1.5.2
numpy==1.24.1
matplotlib==3.6.2
```

**Virtual Environment Best Practices:**

```python
# check_environment.py - Script to check virtual environment
import sys
import os

def check_virtual_env():
    """Check if running in a virtual environment."""
    in_venv = hasattr(sys, 'real_prefix') or (
        hasattr(sys, 'base_prefix') and sys.base_prefix != sys.prefix
    )
    
    if in_venv:
        print("✅ Running in virtual environment")
        print(f"Virtual env path: {sys.prefix}")
    else:
        print("⚠️  Not running in virtual environment")
        print("Consider using: python -m venv myenv")
    
    print(f"Python executable: {sys.executable}")
    print(f"Python version: {sys.version}")

if __name__ == "__main__":
    check_virtual_env()
```

**Practice Exercise - Project Structure:**

Create a complete project with proper structure:

```
calculator_project/
    README.md
    requirements.txt
    setup.py
    calculator/
        __init__.py
        basic_ops.py
        advanced_ops.py
        history.py
    tests/
        __init__.py
        test_basic_ops.py
        test_advanced_ops.py
    examples/
        simple_calculator.py
        advanced_calculator.py
```

**calculator/__init__.py:**

```python
# calculator/__init__.py
"""
A comprehensive calculator package.
"""

__version__ = "1.0.0"
__author__ = "Your Name"

# Import main functions
from .basic_ops import add, subtract, multiply, divide
from .advanced_ops import power, sqrt, factorial
from .history import CalculatorHistory

# Package-level calculator class
class Calculator:
    """Main calculator class combining all operations."""
    
    def __init__(self):
        self.history = CalculatorHistory()
    
    def calculate(self, operation, *args):
        """Perform calculation and store in history."""
        operations = {
            'add': add,
            'subtract': subtract,
            'multiply': multiply,
            'divide': divide,
            'power': power,
            'sqrt': sqrt,
            'factorial': factorial
        }
        
        if operation not in operations:
            raise ValueError(f"Unknown operation: {operation}")
        
        try:
            result = operations[operation](*args)
            self.history.add_calculation(operation, args, result)
            return result
        except Exception as e:
            self.history.add_calculation(operation, args, f"Error: {e}")
            raise

# Make key classes available at package level
__all__ = ['Calculator', 'CalculatorHistory', 'add', 'subtract', 'multiply', 'divide']
```

**calculator/basic_ops.py:**

```python
# calculator/basic_ops.py
"""Basic arithmetic operations."""

def add(a, b):
    """Add two numbers."""
    return a + b

def subtract(a, b):
    """Subtract b from a."""
    return a - b

def multiply(a, b):
    """Multiply two numbers."""
    return a * b

def divide(a, b):
    """Divide a by b."""
    if b == 0:
        raise ValueError("Cannot divide by zero")
    return a / b
```

**Using the Calculator Package:**

```python
# Using the complete calculator package
from calculator import Calculator

# Create calculator instance
calc = Calculator()

# Perform calculations
result1 = calc.calculate('add', 10, 5)
result2 = calc.calculate('multiply', result1, 2)
result3 = calc.calculate('sqrt', 16)

print(f"Results: {result1}, {result2}, {result3}")

# View calculation history
calc.history.show_history()
```

**Key Takeaways:**

- Use `import` statements to access code from other modules
- Create custom modules by writing `.py` files with functions and classes
- Organize related modules into packages using `__init__.py` files
- The standard library provides many useful modules for common tasks
- Virtual environments isolate project dependencies
- Proper project structure makes code maintainable and shareable
- Use `if __name__ == "__main__":` to make modules both importable and executable---

##
 Summary

Congratulations! You've completed the Complete Python Learning Guide. This comprehensive resource has covered:

**Beginner Level:**
- ✅ Basic syntax, variables, and code structure
- ✅ Data types: strings, numbers, booleans, lists, tuples, dictionaries, sets
- ✅ Operators: arithmetic, comparison, logical, assignment
- ✅ Input/output operations and user interaction

**Intermediate Level:**
- ✅ Control structures: if/else, for loops, while loops, break/continue
- ✅ Functions: definition, parameters, return values, scope, lambda functions
- ✅ Error handling: try/except, custom exceptions, debugging techniques

**Advanced Level:**
- ✅ Object-oriented programming basics
- ✅ File handling and data processing

**Professional Level:**
- ✅ Popular libraries overview (NumPy, Pandas, Requests)
- ✅ Best practices and testing
- ✅ Comprehensive resources and career guidance

**What You've Accomplished:**
- Learned Python syntax from basics to advanced concepts
- Practiced with real, runnable code examples
- Built practical projects and exercises
- Gained understanding of professional development practices
- Received guidance for continued learning and career development

**Your Python Journey Continues:**
This guide is just the beginning. Python is a vast and evolving language with endless possibilities. Keep practicing, building projects, and exploring new libraries and frameworks. The Python community is welcoming and supportive - don't hesitate to ask questions and share your progress.

**Remember the key principles:**
- Practice consistently
- Build real projects
- Learn from others' code
- Stay curious and keep experimenting
- Help others learn (teaching reinforces your own knowledge)

Welcome to the Python community! 🐍

---

*Last updated: 2025 | This guide is continuously improved based on community feedback*