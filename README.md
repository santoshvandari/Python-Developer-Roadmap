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

Object-Oriented Programming (OOP) is a programming paradigm that organizes code into classes and objects, making it easier to model real-world entities and relationships.

#### Classes and Objects

**Basic Class Definition:**

```python
class Person:
    """A class representing a person."""
    
    # Class variable (shared by all instances)
    species = "Homo sapiens"
    
    def __init__(self, name, age):
        """Initialize a new Person instance."""
        # Instance variables (unique to each instance)
        self.name = name
        self.age = age
        self.friends = []
    
    def introduce(self):
        """Return an introduction string."""
        return f"Hi, I'm {self.name} and I'm {self.age} years old"
    
    def have_birthday(self):
        """Increase age by 1."""
        self.age += 1
        return f"Happy birthday! {self.name} is now {self.age}"
    
    def add_friend(self, friend):
        """Add a friend to the friends list."""
        if friend not in self.friends:
            self.friends.append(friend)
            return f"{friend} is now {self.name}'s friend"
        return f"{friend} is already {self.name}'s friend"

# Creating objects (instances)
person1 = Person("Alice", 30)
person2 = Person("Bob", 25)

# Using object methods
print(person1.introduce())  # Output: Hi, I'm Alice and I'm 30 years old
print(person1.have_birthday())  # Output: Happy birthday! Alice is now 31

# Accessing attributes
print(f"Name: {person1.name}")  # Output: Name: Alice
print(f"Species: {person1.species}")  # Output: Species: Homo sapiens

# Class variables are shared
print(f"Person1 species: {person1.species}")
print(f"Person2 species: {person2.species}")
Person.species = "Human"  # Changes for all instances
print(f"Person1 species: {person1.species}")  # Output: Human
```

#### Attributes and Methods

**Instance vs Class Attributes:**

```python
class BankAccount:
    """A class representing a bank account."""
    
    # Class variables
    bank_name = "Python Bank"
    interest_rate = 0.02
    total_accounts = 0
    
    def __init__(self, account_holder, initial_balance=0):
        """Initialize a new bank account."""
        # Instance variables
        self.account_holder = account_holder
        self.balance = initial_balance
        self.transaction_history = []
        
        # Increment class variable
        BankAccount.total_accounts += 1
        self.account_number = f"ACC{BankAccount.total_accounts:04d}"
    
    def deposit(self, amount):
        """Deposit money to the account."""
        if amount > 0:
            self.balance += amount
            self.transaction_history.append(f"Deposited ${amount}")
            return f"Deposited ${amount}. New balance: ${self.balance}"
        return "Invalid deposit amount"
    
    def withdraw(self, amount):
        """Withdraw money from the account."""
        if amount > 0 and amount <= self.balance:
            self.balance -= amount
            self.transaction_history.append(f"Withdrew ${amount}")
            return f"Withdrew ${amount}. New balance: ${self.balance}"
        return "Invalid withdrawal amount or insufficient funds"
    
    def get_balance(self):
        """Get current balance."""
        return self.balance
    
    def apply_interest(self):
        """Apply interest to the account."""
        interest = self.balance * self.interest_rate
        self.balance += interest
        self.transaction_history.append(f"Interest applied: ${interest:.2f}")
        return f"Interest applied: ${interest:.2f}"
    
    @classmethod
    def get_bank_info(cls):
        """Get bank information (class method)."""
        return f"Bank: {cls.bank_name}, Total Accounts: {cls.total_accounts}"
    
    @staticmethod
    def validate_account_number(account_number):
        """Validate account number format (static method)."""
        return account_number.startswith("ACC") and len(account_number) == 7

# Using the BankAccount class
account1 = BankAccount("Alice", 1000)
account2 = BankAccount("Bob", 500)

print(account1.deposit(200))
print(account1.withdraw(150))
print(account1.apply_interest())

# Class method usage
print(BankAccount.get_bank_info())

# Static method usage
print(BankAccount.validate_account_number("ACC0001"))  # True
print(BankAccount.validate_account_number("XYZ123"))   # False
```

**Property Decorators:**

```python
class Temperature:
    """A class for temperature conversion with properties."""
    
    def __init__(self, celsius=0):
        """Initialize with Celsius temperature."""
        self._celsius = celsius
    
    @property
    def celsius(self):
        """Get temperature in Celsius."""
        return self._celsius
    
    @celsius.setter
    def celsius(self, value):
        """Set temperature in Celsius with validation."""
        if value < -273.15:
            raise ValueError("Temperature cannot be below absolute zero")
        self._celsius = value
    
    @property
    def fahrenheit(self):
        """Get temperature in Fahrenheit."""
        return (self._celsius * 9/5) + 32
    
    @fahrenheit.setter
    def fahrenheit(self, value):
        """Set temperature using Fahrenheit."""
        self.celsius = (value - 32) * 5/9
    
    @property
    def kelvin(self):
        """Get temperature in Kelvin."""
        return self._celsius + 273.15
    
    @kelvin.setter
    def kelvin(self, value):
        """Set temperature using Kelvin."""
        self.celsius = value - 273.15
    
    def __str__(self):
        """String representation of temperature."""
        return f"{self._celsius}°C ({self.fahrenheit}°F, {self.kelvin}K)"

# Using properties
temp = Temperature(25)
print(temp)  # Output: 25°C (77.0°F, 298.15K)

temp.fahrenheit = 100
print(temp)  # Output: 37.77777777777778°C (100.0°F, 310.92777777777775K)

temp.kelvin = 300
print(temp)  # Output: 26.850000000000023°C (80.33000000000004°F, 300K)
```

#### Inheritance

**Basic Inheritance:**

```python
class Animal:
    """Base class for all animals."""
    
    def __init__(self, name, species):
        self.name = name
        self.species = species
        self.is_alive = True
    
    def eat(self, food):
        return f"{self.name} is eating {food}"
    
    def sleep(self):
        return f"{self.name} is sleeping"
    
    def make_sound(self):
        return f"{self.name} makes a sound"

class Dog(Animal):
    """Dog class inheriting from Animal."""
    
    def __init__(self, name, breed):
        super().__init__(name, "Canis lupus")  # Call parent constructor
        self.breed = breed
        self.tricks = []
    
    def make_sound(self):  # Override parent method
        return f"{self.name} barks: Woof!"
    
    def learn_trick(self, trick):
        self.tricks.append(trick)
        return f"{self.name} learned {trick}"
    
    def perform_trick(self, trick):
        if trick in self.tricks:
            return f"{self.name} performs {trick}"
        return f"{self.name} doesn't know {trick}"

class Cat(Animal):
    """Cat class inheriting from Animal."""
    
    def __init__(self, name, indoor=True):
        super().__init__(name, "Felis catus")
        self.indoor = indoor
        self.lives = 9
    
    def make_sound(self):  # Override parent method
        return f"{self.name} meows: Meow!"
    
    def climb(self):
        return f"{self.name} climbs gracefully"
    
    def use_litter_box(self):
        if self.indoor:
            return f"{self.name} uses the litter box"
        return f"{self.name} goes outside"

# Using inheritance
dog = Dog("Buddy", "Golden Retriever")
cat = Cat("Whiskers", indoor=True)

print(dog.eat("kibble"))      # Inherited method
print(dog.make_sound())       # Overridden method
print(dog.learn_trick("sit")) # Dog-specific method

print(cat.eat("fish"))        # Inherited method
print(cat.make_sound())       # Overridden method
print(cat.climb())            # Cat-specific method
```

**Multiple Inheritance:**

```python
class Flyable:
    """Mixin class for flying ability."""
    
    def fly(self):
        return f"{self.name} is flying"
    
    def land(self):
        return f"{self.name} has landed"

class Swimmable:
    """Mixin class for swimming ability."""
    
    def swim(self):
        return f"{self.name} is swimming"
    
    def dive(self):
        return f"{self.name} dives underwater"

class Bird(Animal, Flyable):
    """Bird class with flying ability."""
    
    def __init__(self, name, wingspan):
        super().__init__(name, "Aves")
        self.wingspan = wingspan
    
    def make_sound(self):
        return f"{self.name} chirps"

class Duck(Bird, Swimmable):
    """Duck class that can both fly and swim."""
    
    def __init__(self, name):
        super().__init__(name, wingspan=24)  # Average duck wingspan in inches
    
    def make_sound(self):
        return f"{self.name} quacks"

# Using multiple inheritance
duck = Duck("Donald")
print(duck.make_sound())  # Output: Donald quacks
print(duck.fly())         # From Flyable mixin
print(duck.swim())        # From Swimmable mixin
print(duck.eat("bread"))  # From Animal base class

# Method Resolution Order (MRO)
print(Duck.__mro__)  # Shows the order Python searches for methods
```

#### Polymorphism

**Method Overriding and Polymorphism:**

```python
class Shape:
    """Base class for geometric shapes."""
    
    def __init__(self, name):
        self.name = name
    
    def area(self):
        """Calculate area - to be overridden by subclasses."""
        raise NotImplementedError("Subclass must implement area method")
    
    def perimeter(self):
        """Calculate perimeter - to be overridden by subclasses."""
        raise NotImplementedError("Subclass must implement perimeter method")
    
    def describe(self):
        """Describe the shape."""
        return f"This is a {self.name}"

class Rectangle(Shape):
    """Rectangle shape."""
    
    def __init__(self, width, height):
        super().__init__("Rectangle")
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height
    
    def perimeter(self):
        return 2 * (self.width + self.height)

class Circle(Shape):
    """Circle shape."""
    
    def __init__(self, radius):
        super().__init__("Circle")
        self.radius = radius
    
    def area(self):
        return 3.14159 * self.radius ** 2
    
    def perimeter(self):
        return 2 * 3.14159 * self.radius

class Triangle(Shape):
    """Triangle shape."""
    
    def __init__(self, side1, side2, side3):
        super().__init__("Triangle")
        self.side1 = side1
        self.side2 = side2
        self.side3 = side3
    
    def area(self):
        # Using Heron's formula
        s = self.perimeter() / 2
        return (s * (s - self.side1) * (s - self.side2) * (s - self.side3)) ** 0.5
    
    def perimeter(self):
        return self.side1 + self.side2 + self.side3

# Polymorphism in action
shapes = [
    Rectangle(5, 4),
    Circle(3),
    Triangle(3, 4, 5)
]

# Same method calls work on different object types
for shape in shapes:
    print(f"{shape.describe()}")
    print(f"Area: {shape.area():.2f}")
    print(f"Perimeter: {shape.perimeter():.2f}")
    print("-" * 30)
```

#### Encapsulation

**Private and Protected Attributes:**

```python
class BankAccount:
    """Demonstrates encapsulation with private attributes."""
    
    def __init__(self, account_holder, initial_balance=0):
        self.account_holder = account_holder  # Public
        self._account_number = self._generate_account_number()  # Protected
        self.__balance = initial_balance  # Private
        self.__pin = None  # Private
    
    def _generate_account_number(self):
        """Protected method - internal use."""
        import random
        return f"ACC{random.randint(10000, 99999)}"
    
    def __validate_transaction(self, amount):
        """Private method - internal validation."""
        return isinstance(amount, (int, float)) and amount > 0
    
    def set_pin(self, pin):
        """Set account PIN."""
        if len(str(pin)) == 4:
            self.__pin = pin
            return "PIN set successfully"
        return "PIN must be 4 digits"
    
    def deposit(self, amount, pin=None):
        """Deposit money with optional PIN verification."""
        if not self.__validate_transaction(amount):
            return "Invalid amount"
        
        if self.__pin and pin != self.__pin:
            return "Invalid PIN"
        
        self.__balance += amount
        return f"Deposited ${amount}. New balance: ${self.__balance}"
    
    def withdraw(self, amount, pin):
        """Withdraw money with PIN verification."""
        if not self.__validate_transaction(amount):
            return "Invalid amount"
        
        if pin != self.__pin:
            return "Invalid PIN"
        
        if amount > self.__balance:
            return "Insufficient funds"
        
        self.__balance -= amount
        return f"Withdrew ${amount}. New balance: ${self.__balance}"
    
    def get_balance(self, pin):
        """Get balance with PIN verification."""
        if pin != self.__pin:
            return "Invalid PIN"
        return self.__balance
    
    @property
    def account_info(self):
        """Get public account information."""
        return {
            "holder": self.account_holder,
            "account_number": self._account_number
        }

# Using encapsulation
account = BankAccount("Alice", 1000)

# Public access
print(account.account_holder)  # Works
print(account.account_info)    # Works

# Protected access (by convention, shouldn't be used externally)
print(account._account_number)  # Works but not recommended

# Private access (name mangling makes it harder to access)
# print(account.__balance)  # AttributeError
# print(account._BankAccount__balance)  # Works but strongly discouraged

# Proper way to access private data
account.set_pin(1234)
print(account.get_balance(1234))  # Output: 1000
print(account.withdraw(200, 1234))  # Output: Withdrew $200. New balance: $800
```

#### Special Methods

**Magic Methods (Dunder Methods):**

```python
class Vector:
    """A 2D vector class demonstrating special methods."""
    
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __str__(self):
        """String representation for users."""
        return f"Vector({self.x}, {self.y})"
    
    def __repr__(self):
        """String representation for developers."""
        return f"Vector(x={self.x}, y={self.y})"
    
    def __add__(self, other):
        """Add two vectors."""
        if isinstance(other, Vector):
            return Vector(self.x + other.x, self.y + other.y)
        return NotImplemented
    
    def __sub__(self, other):
        """Subtract two vectors."""
        if isinstance(other, Vector):
            return Vector(self.x - other.x, self.y - other.y)
        return NotImplemented
    
    def __mul__(self, scalar):
        """Multiply vector by scalar."""
        if isinstance(scalar, (int, float)):
            return Vector(self.x * scalar, self.y * scalar)
        return NotImplemented
    
    def __rmul__(self, scalar):
        """Right multiplication (scalar * vector)."""
        return self.__mul__(scalar)
    
    def __eq__(self, other):
        """Check equality."""
        if isinstance(other, Vector):
            return self.x == other.x and self.y == other.y
        return False
    
    def __lt__(self, other):
        """Less than comparison (by magnitude)."""
        if isinstance(other, Vector):
            return self.magnitude() < other.magnitude()
        return NotImplemented
    
    def __len__(self):
        """Return magnitude as length."""
        return int(self.magnitude())
    
    def __getitem__(self, index):
        """Allow indexing."""
        if index == 0:
            return self.x
        elif index == 1:
            return self.y
        else:
            raise IndexError("Vector index out of range")
    
    def __setitem__(self, index, value):
        """Allow item assignment."""
        if index == 0:
            self.x = value
        elif index == 1:
            self.y = value
        else:
            raise IndexError("Vector index out of range")
    
    def magnitude(self):
        """Calculate vector magnitude."""
        return (self.x ** 2 + self.y ** 2) ** 0.5
    
    def normalize(self):
        """Return normalized vector."""
        mag = self.magnitude()
        if mag == 0:
            return Vector(0, 0)
        return Vector(self.x / mag, self.y / mag)

# Using special methods
v1 = Vector(3, 4)
v2 = Vector(1, 2)

print(v1)           # Output: Vector(3, 4) (uses __str__)
print(repr(v1))     # Output: Vector(x=3, y=4) (uses __repr__)

# Arithmetic operations
v3 = v1 + v2        # Uses __add__
print(v3)           # Output: Vector(4, 6)

v4 = v1 * 2         # Uses __mul__
print(v4)           # Output: Vector(6, 8)

v5 = 3 * v1         # Uses __rmul__
print(v5)           # Output: Vector(9, 12)

# Comparison operations
print(v1 == v2)     # Output: False (uses __eq__)
print(v1 < v2)      # Output: False (uses __lt__)

# Length and indexing
print(len(v1))      # Output: 5 (uses __len__)
print(v1[0])        # Output: 3 (uses __getitem__)
v1[1] = 5           # Uses __setitem__
print(v1)           # Output: Vector(3, 5)
```

**Practice Exercise - Complete OOP System:**

```python
class Library:
    """A complete library management system demonstrating OOP principles."""
    
    def __init__(self, name):
        self.name = name
        self._books = []
        self._members = []
        self._borrowed_books = {}
    
    def add_book(self, book):
        """Add a book to the library."""
        self._books.append(book)
        return f"Added '{book.title}' to {self.name}"
    
    def add_member(self, member):
        """Add a member to the library."""
        self._members.append(member)
        return f"Added member: {member.name}"
    
    def borrow_book(self, member, book_title):
        """Allow a member to borrow a book."""
        book = self._find_book(book_title)
        if not book:
            return f"Book '{book_title}' not found"
        
        if book.is_available:
            book.borrow()
            if member.member_id not in self._borrowed_books:
                self._borrowed_books[member.member_id] = []
            self._borrowed_books[member.member_id].append(book)
            return f"{member.name} borrowed '{book.title}'"
        else:
            return f"'{book.title}' is not available"
    
    def return_book(self, member, book_title):
        """Allow a member to return a book."""
        if member.member_id in self._borrowed_books:
            for book in self._borrowed_books[member.member_id]:
                if book.title == book_title:
                    book.return_book()
                    self._borrowed_books[member.member_id].remove(book)
                    return f"{member.name} returned '{book.title}'"
        return f"Book '{book_title}' was not borrowed by {member.name}"
    
    def _find_book(self, title):
        """Private method to find a book by title."""
        for book in self._books:
            if book.title.lower() == title.lower():
                return book
        return None
    
    def get_available_books(self):
        """Get list of available books."""
        return [book for book in self._books if book.is_available]
    
    def __str__(self):
        return f"Library: {self.name} ({len(self._books)} books, {len(self._members)} members)"

class Book:
    """Book class with encapsulation."""
    
    def __init__(self, title, author, isbn):
        self.title = title
        self.author = author
        self.isbn = isbn
        self._is_available = True
        self._borrow_count = 0
    
    @property
    def is_available(self):
        return self._is_available
    
    def borrow(self):
        """Mark book as borrowed."""
        if self._is_available:
            self._is_available = False
            self._borrow_count += 1
            return True
        return False
    
    def return_book(self):
        """Mark book as returned."""
        self._is_available = True
    
    def __str__(self):
        status = "Available" if self._is_available else "Borrowed"
        return f"'{self.title}' by {self.author} - {status}"
    
    def __eq__(self, other):
        if isinstance(other, Book):
            return self.isbn == other.isbn
        return False

class Member:
    """Library member class."""
    
    _next_id = 1
    
    def __init__(self, name, email):
        self.name = name
        self.email = email
        self.member_id = Member._next_id
        Member._next_id += 1
        self._join_date = "2024-01-01"  # Simplified
    
    def __str__(self):
        return f"Member: {self.name} (ID: {self.member_id})"

# Using the complete OOP system
library = Library("City Library")

# Create books
book1 = Book("Python Programming", "John Doe", "978-1234567890")
book2 = Book("Data Science Handbook", "Jane Smith", "978-0987654321")
book3 = Book("Web Development", "Bob Johnson", "978-1122334455")

# Create members
member1 = Member("Alice Brown", "alice@email.com")
member2 = Member("Charlie Davis", "charlie@email.com")

# Add books and members to library
library.add_book(book1)
library.add_book(book2)
library.add_book(book3)
library.add_member(member1)
library.add_member(member2)

print(library)

# Borrow and return books
print(library.borrow_book(member1, "Python Programming"))
print(library.borrow_book(member2, "Python Programming"))  # Should fail
print(library.return_book(member1, "Python Programming"))
print(library.borrow_book(member2, "Python Programming"))  # Should work now

# Display available books
available = library.get_available_books()
print(f"\nAvailable books: {len(available)}")
for book in available:
    print(f"  {book}")
```

**Key Takeaways:**

- Classes define blueprints for objects with attributes and methods
- Inheritance allows classes to inherit and extend functionality from parent classes
- Polymorphism enables different classes to be used interchangeably through common interfaces
- Encapsulation hides internal implementation details and protects data integrity
- Special methods enable custom behavior for built-in operations
- Use `@property` decorators for controlled attribute access
- Multiple inheritance should be used carefully with mixin classes
- Follow naming conventions: public, _protected, __private

### Advanced Features

Python offers several advanced features that enable more sophisticated programming patterns and improved code efficiency.

#### Decorators

Decorators are a powerful feature that allows you to modify or extend the behavior of functions and classes.

**Function Decorators:**

```python
# Basic decorator
def my_decorator(func):
    """A simple decorator that adds functionality to a function."""
    def wrapper(*args, **kwargs):
        print(f"Before calling {func.__name__}")
        result = func(*args, **kwargs)
        print(f"After calling {func.__name__}")
        return result
    return wrapper

@my_decorator
def greet(name):
    """A simple greeting function."""
    return f"Hello, {name}!"

# Using the decorated function
print(greet("Alice"))
# Output:
# Before calling greet
# Hello, Alice!
# After calling greet

# Decorator with parameters
def repeat(times):
    """Decorator that repeats function execution."""
    def decorator(func):
        def wrapper(*args, **kwargs):
            results = []
            for _ in range(times):
                result = func(*args, **kwargs)
                results.append(result)
            return results
        return wrapper
    return decorator

@repeat(3)
def say_hello():
    return "Hello!"

print(say_hello())  # Output: ['Hello!', 'Hello!', 'Hello!']
```

**Practical Decorators:**

```python
import time
import functools
from datetime import datetime

# Timing decorator
def timer(func):
    """Decorator to measure function execution time."""
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"{func.__name__} took {end_time - start_time:.4f} seconds")
        return result
    return wrapper

# Logging decorator
def log_calls(func):
    """Decorator to log function calls."""
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        timestamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
        print(f"[{timestamp}] Calling {func.__name__} with args={args}, kwargs={kwargs}")
        result = func(*args, **kwargs)
        print(f"[{timestamp}] {func.__name__} returned {result}")
        return result
    return wrapper

# Caching decorator
def memoize(func):
    """Decorator to cache function results."""
    cache = {}
    
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        # Create a key from arguments
        key = str(args) + str(sorted(kwargs.items()))
        
        if key in cache:
            print(f"Cache hit for {func.__name__}")
            return cache[key]
        
        print(f"Cache miss for {func.__name__}")
        result = func(*args, **kwargs)
        cache[key] = result
        return result
    
    return wrapper

# Using multiple decorators
@timer
@log_calls
@memoize
def fibonacci(n):
    """Calculate fibonacci number recursively."""
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

# Test the decorated function
print(f"Fibonacci(10) = {fibonacci(10)}")
print(f"Fibonacci(10) = {fibonacci(10)}")  # Should use cache
```

**Class Decorators:**

```python
def add_string_representation(cls):
    """Class decorator to add string representation."""
    def __str__(self):
        attrs = ', '.join(f"{k}={v}" for k, v in self.__dict__.items())
        return f"{cls.__name__}({attrs})"
    
    cls.__str__ = __str__
    return cls

@add_string_representation
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

person = Person("Alice", 30)
print(person)  # Output: Person(name=Alice, age=30)

# Property decorator for validation
def validate_positive(func):
    """Decorator for property setters to validate positive values."""
    @functools.wraps(func)
    def wrapper(self, value):
        if value <= 0:
            raise ValueError(f"{func.__name__} must be positive")
        return func(self, value)
    return wrapper

class Circle:
    def __init__(self, radius):
        self._radius = radius
    
    @property
    def radius(self):
        return self._radius
    
    @radius.setter
    @validate_positive
    def radius(self, value):
        self._radius = value
    
    @property
    def area(self):
        return 3.14159 * self._radius ** 2

circle = Circle(5)
print(f"Area: {circle.area}")
# circle.radius = -1  # Would raise ValueError
```

#### Generators

Generators are functions that return an iterator object, allowing you to iterate over a sequence of values without storing them all in memory.

**Basic Generators:**

```python
# Generator function
def count_up_to(max_count):
    """Generator that counts from 1 to max_count."""
    count = 1
    while count <= max_count:
        yield count
        count += 1

# Using the generator
counter = count_up_to(5)
print(type(counter))  # Output: <class 'generator'>

for num in counter:
    print(num)  # Output: 1, 2, 3, 4, 5

# Generator expressions
squares = (x**2 for x in range(10))
print(list(squares))  # Output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

# Memory efficient file reading
def read_large_file(file_path):
    """Generator to read large files line by line."""
    try:
        with open(file_path, 'r') as file:
            for line in file:
                yield line.strip()
    except FileNotFoundError:
        print(f"File {file_path} not found")
        return

# Fibonacci generator
def fibonacci_generator():
    """Infinite Fibonacci sequence generator."""
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

# Using Fibonacci generator
fib = fibonacci_generator()
first_10_fibs = [next(fib) for _ in range(10)]
print(first_10_fibs)  # Output: [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
```

**Advanced Generator Patterns:**

```python
# Generator with send() method
def accumulator():
    """Generator that accumulates sent values."""
    total = 0
    while True:
        value = yield total
        if value is not None:
            total += value

acc = accumulator()
next(acc)  # Prime the generator
print(acc.send(10))  # Output: 10
print(acc.send(5))   # Output: 15
print(acc.send(3))   # Output: 18

# Generator pipeline
def numbers():
    """Generate numbers 1-10."""
    for i in range(1, 11):
        yield i

def squares(nums):
    """Square the input numbers."""
    for num in nums:
        yield num ** 2

def even_only(nums):
    """Filter even numbers only."""
    for num in nums:
        if num % 2 == 0:
            yield num

# Chain generators together
pipeline = even_only(squares(numbers()))
result = list(pipeline)
print(result)  # Output: [4, 16, 36, 64, 100]

# Generator for tree traversal
class TreeNode:
    def __init__(self, value, left=None, right=None):
        self.value = value
        self.left = left
        self.right = right

def inorder_traversal(node):
    """Generator for inorder tree traversal."""
    if node:
        yield from inorder_traversal(node.left)
        yield node.value
        yield from inorder_traversal(node.right)

# Create a binary tree
root = TreeNode(4)
root.left = TreeNode(2)
root.right = TreeNode(6)
root.left.left = TreeNode(1)
root.left.right = TreeNode(3)

# Traverse using generator
for value in inorder_traversal(root):
    print(value, end=" ")  # Output: 1 2 3 4 6
print()
```

#### Context Managers

Context managers ensure proper resource management using the `with` statement.

**Built-in Context Managers:**

```python
# File handling with context manager
with open('example.txt', 'w') as file:
    file.write('Hello, World!')
# File is automatically closed

# Multiple context managers
with open('input.txt', 'r') as infile, open('output.txt', 'w') as outfile:
    data = infile.read()
    outfile.write(data.upper())

# Exception handling with context managers
try:
    with open('nonexistent.txt', 'r') as file:
        content = file.read()
except FileNotFoundError:
    print("File not found, but resources are still cleaned up")
```

**Custom Context Managers:**

```python
# Using __enter__ and __exit__ methods
class DatabaseConnection:
    """Custom context manager for database connections."""
    
    def __init__(self, database_name):
        self.database_name = database_name
        self.connection = None
    
    def __enter__(self):
        print(f"Connecting to {self.database_name}")
        self.connection = f"Connection to {self.database_name}"
        return self.connection
    
    def __exit__(self, exc_type, exc_value, traceback):
        print(f"Closing connection to {self.database_name}")
        if exc_type:
            print(f"Exception occurred: {exc_value}")
        self.connection = None
        return False  # Don't suppress exceptions

# Using custom context manager
with DatabaseConnection("mydb") as conn:
    print(f"Using {conn}")
    # Connection is automatically closed

# Context manager using contextlib
from contextlib import contextmanager

@contextmanager
def timer_context(name):
    """Context manager to time code execution."""
    start_time = time.time()
    print(f"Starting {name}")
    try:
        yield
    finally:
        end_time = time.time()
        print(f"{name} took {end_time - start_time:.4f} seconds")

# Using contextlib context manager
with timer_context("Data processing"):
    time.sleep(1)  # Simulate work
    print("Processing data...")

# Temporary directory context manager
import tempfile
import os

@contextmanager
def temporary_directory():
    """Create and cleanup temporary directory."""
    temp_dir = tempfile.mkdtemp()
    try:
        yield temp_dir
    finally:
        import shutil
        shutil.rmtree(temp_dir)

with temporary_directory() as temp_dir:
    print(f"Working in {temp_dir}")
    # Create files, do work...
    temp_file = os.path.join(temp_dir, "temp.txt")
    with open(temp_file, 'w') as f:
        f.write("Temporary data")
# Directory is automatically cleaned up
```

#### List Comprehensions

Advanced list comprehension patterns and related comprehensions.

**Advanced List Comprehensions:**

```python
# Nested list comprehensions
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

# Flatten matrix
flattened = [num for row in matrix for num in row]
print(flattened)  # Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]

# Transpose matrix
transposed = [[row[i] for row in matrix] for i in range(len(matrix[0]))]
print(transposed)  # Output: [[1, 4, 7], [2, 5, 8], [3, 6, 9]]

# Conditional comprehensions
numbers = range(1, 21)
even_squares = [x**2 for x in numbers if x % 2 == 0]
print(even_squares)  # Output: [4, 16, 36, 64, 100, 144, 196, 256, 324, 400]

# Complex conditions
words = ["hello", "world", "python", "programming", "code"]
long_words = [word.upper() for word in words if len(word) > 5 and 'o' in word]
print(long_words)  # Output: ['PYTHON', 'PROGRAMMING']

# Dictionary comprehensions
squares_dict = {x: x**2 for x in range(1, 6)}
print(squares_dict)  # Output: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}

# Set comprehensions
unique_lengths = {len(word) for word in words}
print(unique_lengths)  # Output: {4, 5, 6, 11}

# Generator comprehensions
squares_gen = (x**2 for x in range(1000000))  # Memory efficient
print(sum(x for x in squares_gen if x % 2 == 0 and x < 100))
```

#### Iterators

Understanding and creating custom iterators.

**Custom Iterator Classes:**

```python
class CountDown:
    """Custom iterator that counts down from a given number."""
    
    def __init__(self, start):
        self.start = start
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.start <= 0:
            raise StopIteration
        self.start -= 1
        return self.start + 1

# Using custom iterator
countdown = CountDown(5)
for num in countdown:
    print(num)  # Output: 5, 4, 3, 2, 1

# Iterator with state
class FibonacciIterator:
    """Iterator for Fibonacci sequence."""
    
    def __init__(self, max_count):
        self.max_count = max_count
        self.count = 0
        self.a, self.b = 0, 1
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.count >= self.max_count:
            raise StopIteration
        
        if self.count == 0:
            self.count += 1
            return self.a
        elif self.count == 1:
            self.count += 1
            return self.b
        else:
            self.a, self.b = self.b, self.a + self.b
            self.count += 1
            return self.b

fib_iter = FibonacciIterator(10)
fib_sequence = list(fib_iter)
print(fib_sequence)  # Output: [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
```

#### Advanced Function Features

**Closures and Nonlocal:**

```python
def create_multiplier(factor):
    """Create a function that multiplies by a factor."""
    def multiplier(number):
        return number * factor
    return multiplier

# Create specific multipliers
double = create_multiplier(2)
triple = create_multiplier(3)

print(double(5))  # Output: 10
print(triple(4))  # Output: 12

# Closure with state
def create_counter(initial=0):
    """Create a counter function with state."""
    count = initial
    
    def counter():
        nonlocal count
        count += 1
        return count
    
    def reset():
        nonlocal count
        count = initial
    
    def get_count():
        return count
    
    # Return multiple functions
    counter.reset = reset
    counter.get_count = get_count
    return counter

# Using closure with state
my_counter = create_counter(10)
print(my_counter())  # Output: 11
print(my_counter())  # Output: 12
print(my_counter.get_count())  # Output: 12
my_counter.reset()
print(my_counter())  # Output: 11

# Partial functions
from functools import partial

def power(base, exponent):
    return base ** exponent

# Create specialized functions
square = partial(power, exponent=2)
cube = partial(power, exponent=3)

print(square(5))  # Output: 25
print(cube(3))    # Output: 27

# Higher-order functions
def apply_operation(operation, *args):
    """Apply an operation to arguments."""
    return operation(*args)

def compose(*functions):
    """Compose multiple functions."""
    def composed(x):
        for func in reversed(functions):
            x = func(x)
        return x
    return composed

# Using higher-order functions
add_one = lambda x: x + 1
multiply_by_two = lambda x: x * 2
square_func = lambda x: x ** 2

# Compose functions
complex_operation = compose(square_func, multiply_by_two, add_one)
result = complex_operation(3)  # ((3 + 1) * 2) ** 2 = 64
print(result)  # Output: 64
```

**Practice Exercise - Advanced Features Integration:**

```python
import time
import functools
from contextlib import contextmanager
from typing import Iterator, Callable, Any

class AdvancedDataProcessor:
    """Demonstrates integration of advanced Python features."""
    
    def __init__(self):
        self._cache = {}
        self._processing_stats = {"calls": 0, "cache_hits": 0}
    
    @contextmanager
    def processing_timer(self, operation_name: str):
        """Context manager for timing operations."""
        start_time = time.time()
        print(f"Starting {operation_name}...")
        try:
            yield
        finally:
            end_time = time.time()
            print(f"{operation_name} completed in {end_time - start_time:.4f}s")
    
    def cache_results(self, func: Callable) -> Callable:
        """Decorator to cache function results."""
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            # Create cache key
            key = str(args) + str(sorted(kwargs.items()))
            
            self._processing_stats["calls"] += 1
            
            if key in self._cache:
                self._processing_stats["cache_hits"] += 1
                print(f"Cache hit for {func.__name__}")
                return self._cache[key]
            
            result = func(*args, **kwargs)
            self._cache[key] = result
            return result
        return wrapper
    
    def data_generator(self, data_source: list) -> Iterator[Any]:
        """Generator for processing data items."""
        for item in data_source:
            # Simulate processing time
            time.sleep(0.01)
            yield self._transform_item(item)
    
    def _transform_item(self, item: Any) -> Any:
        """Transform a single data item."""
        if isinstance(item, (int, float)):
            return item ** 2
        elif isinstance(item, str):
            return item.upper()
        else:
            return str(item)
    
    @cache_results
    def expensive_calculation(self, n: int) -> int:
        """Simulate an expensive calculation."""
        time.sleep(0.1)  # Simulate work
        return sum(i ** 2 for i in range(n))
    
    def process_data_pipeline(self, data: list) -> list:
        """Process data using generator pipeline."""
        # Generator pipeline
        processed = self.data_generator(data)
        filtered = (item for item in processed if self._should_include(item))
        
        return list(filtered)
    
    def _should_include(self, item: Any) -> bool:
        """Filter criteria for processed items."""
        if isinstance(item, (int, float)):
            return item > 10
        elif isinstance(item, str):
            return len(item) > 3
        return True
    
    def batch_process(self, data_batches: list) -> dict:
        """Process multiple batches with timing and caching."""
        results = {}
        
        for i, batch in enumerate(data_batches):
            batch_name = f"batch_{i+1}"
            
            with self.processing_timer(f"Processing {batch_name}"):
                # Use list comprehension with caching
                batch_results = [
                    self.expensive_calculation(item) 
                    for item in batch 
                    if isinstance(item, int) and item > 0
                ]
                
                results[batch_name] = {
                    "processed_items": len(batch_results),
                    "total": sum(batch_results),
                    "average": sum(batch_results) / len(batch_results) if batch_results else 0
                }
        
        return results
    
    def get_stats(self) -> dict:
        """Get processing statistics."""
        hit_rate = (self._processing_stats["cache_hits"] / 
                   self._processing_stats["calls"] * 100 
                   if self._processing_stats["calls"] > 0 else 0)
        
        return {
            "total_calls": self._processing_stats["calls"],
            "cache_hits": self._processing_stats["cache_hits"],
            "cache_hit_rate": f"{hit_rate:.1f}%",
            "cached_results": len(self._cache)
        }

# Using the advanced data processor
processor = AdvancedDataProcessor()

# Test data
test_data = [1, 2, 3, "hello", "world", 4.5, "python"]
data_batches = [[1, 2, 3], [2, 3, 4], [1, 5, 6]]  # Some repeated values for cache testing

print("=== Advanced Features Demo ===")

# Test generator pipeline
with processor.processing_timer("Data pipeline"):
    pipeline_results = processor.process_data_pipeline(test_data)
    print(f"Pipeline results: {pipeline_results}")

# Test batch processing with caching
batch_results = processor.batch_process(data_batches)
print(f"\nBatch results: {batch_results}")

# Show statistics
stats = processor.get_stats()
print(f"\nProcessing statistics: {stats}")
```

**Key Takeaways:**

- Decorators modify function behavior and can be stacked for multiple effects
- Generators provide memory-efficient iteration over large datasets
- Context managers ensure proper resource management and cleanup
- List comprehensions offer concise syntax for data transformation
- Custom iterators provide fine-grained control over iteration behavior
- Closures capture variables from enclosing scopes for stateful functions
- Advanced features work together to create powerful, efficient programs

### File Handling

File handling is essential for reading data, storing results, and working with external resources. Python provides comprehensive tools for working with various file formats.

#### Reading and Writing Files

**Basic File Operations:**

```python
# Writing to a file
with open("example.txt", "w") as file:
    file.write("Hello, World!\n")
    file.write("Python is awesome!\n")
    file.write("File handling is important.")

# Reading entire file
with open("example.txt", "r") as file:
    content = file.read()
    print("Full content:")
    print(content)

# Reading line by line
with open("example.txt", "r") as file:
    print("\nLine by line:")
    for line_number, line in enumerate(file, 1):
        print(f"Line {line_number}: {line.strip()}")

# Reading all lines into a list
with open("example.txt", "r") as file:
    lines = file.readlines()
    print(f"\nTotal lines: {len(lines)}")
    print("Lines as list:", [line.strip() for line in lines])
```

**Different File Modes:**

```python
# File modes demonstration
modes_demo = {
    'w': 'Write mode - overwrites existing file',
    'a': 'Append mode - adds to end of file',
    'r': 'Read mode - read only',
    'x': 'Exclusive creation - fails if file exists',
    'b': 'Binary mode - for binary files',
    't': 'Text mode - default for text files',
    '+': 'Read and write mode'
}

# Append to file
with open("example.txt", "a") as file:
    file.write("\nThis line was appended.")

# Read and write mode
with open("example.txt", "r+") as file:
    content = file.read()
    file.write("\nAdded in r+ mode")

# Working with file positions
with open("example.txt", "r") as file:
    print(f"Current position: {file.tell()}")
    first_line = file.readline()
    print(f"After reading first line: {file.tell()}")
    file.seek(0)  # Go back to beginning
    print(f"After seek(0): {file.tell()}")
```

**Error Handling with Files:**

```python
def safe_file_operations(filename):
    """Demonstrate safe file operations with error handling."""
    
    # Reading with error handling
    try:
        with open(filename, 'r') as file:
            content = file.read()
            return content
    except FileNotFoundError:
        print(f"Error: File '{filename}' not found")
        return None
    except PermissionError:
        print(f"Error: Permission denied to read '{filename}'")
        return None
    except Exception as e:
        print(f"Unexpected error reading '{filename}': {e}")
        return None

# Writing with error handling
def safe_write_file(filename, content):
    """Safely write content to file."""
    try:
        with open(filename, 'w') as file:
            file.write(content)
        print(f"Successfully wrote to '{filename}'")
        return True
    except PermissionError:
        print(f"Error: Permission denied to write '{filename}'")
        return False
    except Exception as e:
        print(f"Unexpected error writing '{filename}': {e}")
        return False

# Test safe operations
content = safe_file_operations("example.txt")
if content:
    print("File content retrieved successfully")

safe_write_file("test_output.txt", "This is a test file.")
```

#### Working with CSV Files

**Basic CSV Operations:**

```python
import csv
from datetime import datetime

# Writing CSV files
def create_employee_csv():
    """Create a CSV file with employee data."""
    employees = [
        ["Name", "Age", "Department", "Salary", "Start Date"],
        ["Alice Johnson", 30, "Engineering", 75000, "2022-01-15"],
        ["Bob Smith", 25, "Marketing", 55000, "2022-03-01"],
        ["Charlie Brown", 35, "Engineering", 85000, "2021-06-10"],
        ["Diana Prince", 28, "HR", 60000, "2022-02-20"],
        ["Eve Wilson", 32, "Finance", 70000, "2021-11-05"]
    ]
    
    with open("employees.csv", "w", newline="", encoding="utf-8") as file:
        writer = csv.writer(file)
        writer.writerows(employees)
    
    print("Employee CSV file created successfully")

# Reading CSV files
def read_employee_csv():
    """Read and process employee CSV data."""
    try:
        with open("employees.csv", "r", encoding="utf-8") as file:
            reader = csv.reader(file)
            headers = next(reader)  # Get headers
            
            print("Employee Data:")
            print("-" * 60)
            
            employees = []
            for row in reader:
                employee = dict(zip(headers, row))
                employees.append(employee)
                print(f"{employee['Name']:<15} | {employee['Department']:<12} | ${employee['Salary']}")
            
            return employees
    
    except FileNotFoundError:
        print("Employee CSV file not found")
        return []

# Using DictReader and DictWriter
def advanced_csv_operations():
    """Demonstrate advanced CSV operations."""
    
    # Reading with DictReader
    try:
        with open("employees.csv", "r") as file:
            reader = csv.DictReader(file)
            
            # Filter and process data
            engineering_employees = []
            for row in reader:
                if row["Department"] == "Engineering":
                    engineering_employees.append(row)
            
            print(f"\nEngineering Department ({len(engineering_employees)} employees):")
            for emp in engineering_employees:
                print(f"  {emp['Name']} - ${emp['Salary']}")
    
    except FileNotFoundError:
        print("CSV file not found")
        return
    
    # Writing with DictWriter
    summary_data = [
        {"Department": "Engineering", "Count": 2, "Avg_Salary": 80000},
        {"Department": "Marketing", "Count": 1, "Avg_Salary": 55000},
        {"Department": "HR", "Count": 1, "Avg_Salary": 60000},
        {"Department": "Finance", "Count": 1, "Avg_Salary": 70000}
    ]
    
    with open("department_summary.csv", "w", newline="") as file:
        fieldnames = ["Department", "Count", "Avg_Salary"]
        writer = csv.DictWriter(file, fieldnames=fieldnames)
        
        writer.writeheader()
        writer.writerows(summary_data)
    
    print("Department summary CSV created")

# Run CSV operations
create_employee_csv()
employees = read_employee_csv()
advanced_csv_operations()
```

#### JSON File Operations

**Working with JSON Data:**

```python
import json
from datetime import datetime, date

# Custom JSON encoder for dates
class DateTimeEncoder(json.JSONEncoder):
    """Custom JSON encoder for datetime objects."""
    
    def default(self, obj):
        if isinstance(obj, (datetime, date)):
            return obj.isoformat()
        return super().default(obj)

# Writing JSON files
def create_json_data():
    """Create and write JSON data."""
    
    # Complex data structure
    company_data = {
        "company": {
            "name": "Tech Solutions Inc.",
            "founded": date(2020, 1, 15),
            "employees": [
                {
                    "id": 1,
                    "name": "Alice Johnson",
                    "position": "Senior Developer",
                    "skills": ["Python", "JavaScript", "SQL"],
                    "hire_date": date(2022, 1, 15),
                    "salary": 75000,
                    "active": True
                },
                {
                    "id": 2,
                    "name": "Bob Smith",
                    "position": "Marketing Manager",
                    "skills": ["Marketing", "Analytics", "Communication"],
                    "hire_date": date(2022, 3, 1),
                    "salary": 55000,
                    "active": True
                }
            ],
            "departments": {
                "engineering": {"budget": 500000, "head": "Alice Johnson"},
                "marketing": {"budget": 200000, "head": "Bob Smith"}
            }
        }
    }
    
    # Write JSON with custom encoder
    with open("company_data.json", "w") as file:
        json.dump(company_data, file, cls=DateTimeEncoder, indent=2)
    
    print("Company JSON data created")
    return company_data

# Reading JSON files
def read_json_data():
    """Read and process JSON data."""
    try:
        with open("company_data.json", "r") as file:
            data = json.load(file)
        
        company = data["company"]
        print(f"Company: {company['name']}")
        print(f"Founded: {company['founded']}")
        print(f"Employees: {len(company['employees'])}")
        
        # Process employee data
        print("\nEmployee Details:")
        for emp in company["employees"]:
            skills_str = ", ".join(emp["skills"])
            print(f"  {emp['name']} - {emp['position']}")
            print(f"    Skills: {skills_str}")
            print(f"    Salary: ${emp['salary']:,}")
        
        return data
    
    except FileNotFoundError:
        print("JSON file not found")
        return None
    except json.JSONDecodeError as e:
        print(f"Error parsing JSON: {e}")
        return None

# JSON manipulation
def update_json_data():
    """Update existing JSON data."""
    data = read_json_data()
    if not data:
        return
    
    # Add new employee
    new_employee = {
        "id": 3,
        "name": "Charlie Brown",
        "position": "Data Analyst",
        "skills": ["Python", "SQL", "Statistics"],
        "hire_date": "2023-01-10",
        "salary": 65000,
        "active": True
    }
    
    data["company"]["employees"].append(new_employee)
    
    # Update department budget
    data["company"]["departments"]["engineering"]["budget"] = 600000
    
    # Write updated data
    with open("company_data_updated.json", "w") as file:
        json.dump(data, file, indent=2)
    
    print("JSON data updated and saved")

# Run JSON operations
original_data = create_json_data()
read_data = read_json_data()
update_json_data()
```

#### File Paths with Pathlib

**Modern Path Handling:**

```python
from pathlib import Path
import os
import shutil
from datetime import datetime

# Creating Path objects
def pathlib_basics():
    """Demonstrate basic pathlib operations."""
    
    # Current working directory
    current_dir = Path.cwd()
    print(f"Current directory: {current_dir}")
    
    # Home directory
    home_dir = Path.home()
    print(f"Home directory: {home_dir}")
    
    # Creating paths
    data_dir = Path("data")
    file_path = data_dir / "example.txt"
    
    print(f"Data directory: {data_dir}")
    print(f"File path: {file_path}")
    
    # Path properties
    if file_path.exists():
        print(f"File name: {file_path.name}")
        print(f"File stem: {file_path.stem}")
        print(f"File suffix: {file_path.suffix}")
        print(f"Parent directory: {file_path.parent}")
        print(f"Absolute path: {file_path.absolute()}")

# File system operations with pathlib
def pathlib_file_operations():
    """Demonstrate file operations with pathlib."""
    
    # Create directory structure
    project_dir = Path("my_project")
    src_dir = project_dir / "src"
    data_dir = project_dir / "data"
    docs_dir = project_dir / "docs"
    
    # Create directories
    for directory in [src_dir, data_dir, docs_dir]:
        directory.mkdir(parents=True, exist_ok=True)
        print(f"Created directory: {directory}")
    
    # Create files
    files_to_create = [
        (src_dir / "main.py", "# Main application file\nprint('Hello, World!')"),
        (src_dir / "utils.py", "# Utility functions\ndef helper():\n    pass"),
        (data_dir / "sample.txt", "Sample data file\nLine 2\nLine 3"),
        (docs_dir / "README.md", "# My Project\nThis is a sample project.")
    ]
    
    for file_path, content in files_to_create:
        file_path.write_text(content)
        print(f"Created file: {file_path}")
    
    return project_dir

# Directory traversal and file searching
def explore_directory_structure(root_path):
    """Explore directory structure using pathlib."""
    
    root = Path(root_path)
    if not root.exists():
        print(f"Directory {root_path} does not exist")
        return
    
    print(f"\nExploring directory: {root}")
    print("=" * 50)
    
    # Recursive directory listing
    for item in root.rglob("*"):
        indent = "  " * (len(item.parts) - len(root.parts))
        if item.is_file():
            size = item.stat().st_size
            modified = datetime.fromtimestamp(item.stat().st_mtime)
            print(f"{indent}📄 {item.name} ({size} bytes, modified: {modified.strftime('%Y-%m-%d %H:%M')})")
        elif item.is_dir():
            print(f"{indent}📁 {item.name}/")
    
    # Find specific file types
    print(f"\nPython files in {root}:")
    for py_file in root.rglob("*.py"):
        print(f"  {py_file}")
    
    print(f"\nText files in {root}:")
    for txt_file in root.rglob("*.txt"):
        print(f"  {txt_file}")

# File operations and utilities
def file_utilities():
    """Demonstrate various file utilities."""
    
    # File information
    def get_file_info(file_path):
        """Get detailed file information."""
        path = Path(file_path)
        if not path.exists():
            return f"File {file_path} does not exist"
        
        stat = path.stat()
        info = {
            "name": path.name,
            "size": stat.st_size,
            "created": datetime.fromtimestamp(stat.st_ctime),
            "modified": datetime.fromtimestamp(stat.st_mtime),
            "is_file": path.is_file(),
            "is_directory": path.is_dir(),
            "absolute_path": path.absolute()
        }
        return info
    
    # Copy files
    def copy_file_with_backup(source, destination):
        """Copy file with backup if destination exists."""
        src = Path(source)
        dst = Path(destination)
        
        if not src.exists():
            return f"Source file {source} does not exist"
        
        if dst.exists():
            backup_name = f"{dst.stem}_backup_{datetime.now().strftime('%Y%m%d_%H%M%S')}{dst.suffix}"
            backup_path = dst.parent / backup_name
            shutil.copy2(dst, backup_path)
            print(f"Created backup: {backup_path}")
        
        shutil.copy2(src, dst)
        return f"Copied {source} to {destination}"
    
    # Example usage
    project_dir = Path("my_project")
    if project_dir.exists():
        sample_file = project_dir / "data" / "sample.txt"
        if sample_file.exists():
            info = get_file_info(sample_file)
            print("File information:")
            for key, value in info.items():
                print(f"  {key}: {value}")
            
            # Copy with backup
            backup_result = copy_file_with_backup(
                sample_file, 
                project_dir / "data" / "sample_copy.txt"
            )
            print(backup_result)

# Run pathlib demonstrations
pathlib_basics()
project_dir = pathlib_file_operations()
explore_directory_structure(project_dir)
file_utilities()
```

#### Binary Files

**Working with Binary Data:**

```python
import struct
import pickle

# Reading and writing binary files
def binary_file_operations():
    """Demonstrate binary file operations."""
    
    # Writing binary data
    binary_data = b"Hello, binary world!\x00\x01\x02\x03"
    
    with open("binary_example.bin", "wb") as file:
        file.write(binary_data)
    
    print("Binary data written")
    
    # Reading binary data
    with open("binary_example.bin", "rb") as file:
        read_data = file.read()
        print(f"Read binary data: {read_data}")
        print(f"As hex: {read_data.hex()}")

# Working with structured binary data
def structured_binary_data():
    """Work with structured binary data using struct module."""
    
    # Pack data into binary format
    # Format: int (4 bytes), float (4 bytes), string (10 bytes)
    data_to_pack = [
        (1, 3.14, b"Alice     "),
        (2, 2.71, b"Bob       "),
        (3, 1.41, b"Charlie   ")
    ]
    
    with open("structured_data.bin", "wb") as file:
        for record in data_to_pack:
            # 'I' = unsigned int, 'f' = float, '10s' = 10-byte string
            packed_data = struct.pack('If10s', *record)
            file.write(packed_data)
    
    print("Structured binary data written")
    
    # Read structured binary data
    with open("structured_data.bin", "rb") as file:
        print("Reading structured data:")
        record_size = struct.calcsize('If10s')
        
        while True:
            data = file.read(record_size)
            if not data:
                break
            
            unpacked = struct.unpack('If10s', data)
            id_num, value, name = unpacked
            name_str = name.decode('utf-8').strip()
            print(f"ID: {id_num}, Value: {value:.2f}, Name: {name_str}")

# Object serialization with pickle
def pickle_operations():
    """Demonstrate object serialization with pickle."""
    
    # Complex data structure
    data_to_serialize = {
        "users": [
            {"id": 1, "name": "Alice", "scores": [95, 87, 92]},
            {"id": 2, "name": "Bob", "scores": [88, 91, 85]}
        ],
        "metadata": {
            "created": "2024-01-01",
            "version": 1.0,
            "settings": {"theme": "dark", "language": "en"}
        }
    }
    
    # Serialize to file
    with open("data.pickle", "wb") as file:
        pickle.dump(data_to_serialize, file)
    
    print("Data serialized with pickle")
    
    # Deserialize from file
    with open("data.pickle", "rb") as file:
        loaded_data = pickle.load(file)
    
    print("Loaded data:")
    print(f"Users: {len(loaded_data['users'])}")
    for user in loaded_data["users"]:
        avg_score = sum(user["scores"]) / len(user["scores"])
        print(f"  {user['name']}: Average score {avg_score:.1f}")

# Run binary file demonstrations
binary_file_operations()
structured_binary_data()
pickle_operations()
```

#### File System Operations

**Advanced File System Operations:**

```python
import os
import shutil
import glob
from pathlib import Path
import tempfile

def file_system_operations():
    """Demonstrate comprehensive file system operations."""
    
    # Create temporary directory for demonstrations
    with tempfile.TemporaryDirectory() as temp_dir:
        temp_path = Path(temp_dir)
        print(f"Working in temporary directory: {temp_path}")
        
        # Create directory structure
        dirs_to_create = [
            "projects/web_app/src",
            "projects/web_app/tests",
            "projects/data_analysis/notebooks",
            "projects/data_analysis/data",
            "backup",
            "archive"
        ]
        
        for dir_path in dirs_to_create:
            (temp_path / dir_path).mkdir(parents=True, exist_ok=True)
        
        # Create sample files
        files_to_create = [
            ("projects/web_app/src/app.py", "# Web application\nprint('Hello, Web!')"),
            ("projects/web_app/src/utils.py", "# Utilities\ndef helper(): pass"),
            ("projects/web_app/tests/test_app.py", "# Tests\ndef test_app(): pass"),
            ("projects/data_analysis/notebooks/analysis.ipynb", '{"cells": []}'),
            ("projects/data_analysis/data/dataset.csv", "name,age\nAlice,30\nBob,25"),
            ("README.md", "# Project Repository\nThis is a sample repository."),
            ("requirements.txt", "flask==2.0.1\npandas==1.3.0")
        ]
        
        for file_path, content in files_to_create:
            full_path = temp_path / file_path
            full_path.write_text(content)
        
        print("Created directory structure and files")
        
        # File searching with glob patterns
        print("\nSearching for files:")
        
        # Find all Python files
        python_files = list(temp_path.rglob("*.py"))
        print(f"Python files: {len(python_files)}")
        for py_file in python_files:
            print(f"  {py_file.relative_to(temp_path)}")
        
        # Find files in specific directory
        web_app_files = list((temp_path / "projects/web_app").rglob("*"))
        print(f"\nWeb app files: {len([f for f in web_app_files if f.is_file()])}")
        
        # Copy operations
        print("\nFile operations:")
        
        # Copy single file
        src_file = temp_path / "projects/web_app/src/app.py"
        backup_file = temp_path / "backup/app_backup.py"
        shutil.copy2(src_file, backup_file)
        print(f"Copied {src_file.name} to backup")
        
        # Copy entire directory
        src_dir = temp_path / "projects/web_app"
        archive_dir = temp_path / "archive/web_app_archive"
        shutil.copytree(src_dir, archive_dir)
        print(f"Copied entire web_app directory to archive")
        
        # Move operations
        old_path = temp_path / "requirements.txt"
        new_path = temp_path / "projects/requirements.txt"
        shutil.move(str(old_path), str(new_path))
        print(f"Moved requirements.txt to projects directory")
        
        # Directory size calculation
        def get_directory_size(path):
            """Calculate total size of directory."""
            total_size = 0
            for file_path in path.rglob("*"):
                if file_path.is_file():
                    total_size += file_path.stat().st_size
            return total_size
        
        projects_size = get_directory_size(temp_path / "projects")
        print(f"\nProjects directory size: {projects_size} bytes")
        
        # File filtering and processing
        def process_python_files(root_path):
            """Process all Python files in directory."""
            python_files = list(root_path.rglob("*.py"))
            
            stats = {
                "total_files": len(python_files),
                "total_lines": 0,
                "files_with_imports": 0
            }
            
            for py_file in python_files:
                try:
                    content = py_file.read_text()
                    lines = content.split('\n')
                    stats["total_lines"] += len(lines)
                    
                    if any(line.strip().startswith(('import ', 'from ')) for line in lines):
                        stats["files_with_imports"] += 1
                
                except Exception as e:
                    print(f"Error processing {py_file}: {e}")
            
            return stats
        
        py_stats = process_python_files(temp_path)
        print(f"\nPython files statistics:")
        for key, value in py_stats.items():
            print(f"  {key}: {value}")

# File monitoring and watching (conceptual example)
def file_monitoring_example():
    """Example of file monitoring concepts."""
    
    def monitor_directory_changes(directory_path, duration=5):
        """Monitor directory for changes (simplified example)."""
        path = Path(directory_path)
        if not path.exists():
            print(f"Directory {directory_path} does not exist")
            return
        
        print(f"Monitoring {directory_path} for {duration} seconds...")
        
        # Get initial state
        initial_files = {f: f.stat().st_mtime for f in path.rglob("*") if f.is_file()}
        
        import time
        time.sleep(duration)
        
        # Check for changes
        current_files = {f: f.stat().st_mtime for f in path.rglob("*") if f.is_file()}
        
        # Find new files
        new_files = set(current_files.keys()) - set(initial_files.keys())
        if new_files:
            print("New files detected:")
            for file_path in new_files:
                print(f"  + {file_path}")
        
        # Find modified files
        modified_files = []
        for file_path, mtime in current_files.items():
            if file_path in initial_files and initial_files[file_path] != mtime:
                modified_files.append(file_path)
        
        if modified_files:
            print("Modified files:")
            for file_path in modified_files:
                print(f"  ~ {file_path}")
        
        # Find deleted files
        deleted_files = set(initial_files.keys()) - set(current_files.keys())
        if deleted_files:
            print("Deleted files:")
            for file_path in deleted_files:
                print(f"  - {file_path}")
        
        if not (new_files or modified_files or deleted_files):
            print("No changes detected")

# Run file system operations
file_system_operations()

print("\n" + "="*50)
print("File monitoring example (create/modify files in current directory):")
# monitor_directory_changes(".", 10)  # Uncomment to test monitoring
```

**Key Takeaways:**

- Always use context managers (`with` statement) for file operations
- Handle file-related exceptions appropriately
- Use pathlib for modern, cross-platform path handling
- CSV and JSON modules provide robust data file handling
- Binary files require special handling with struct and pickle
- File system operations should be performed carefully with proper error handling
- Consider using temporary directories for testing and intermediate files

## Professional Level

### Popular Libraries

#### NumPy for Numerical Computing

NumPy is the foundation of scientific computing in Python, providing powerful array operations and mathematical functions.

**Array Creation and Basic Operations:**

```python
import numpy as np

# Creating arrays
arr1d = np.array([1, 2, 3, 4, 5])
arr2d = np.array([[1, 2, 3], [4, 5, 6]])
zeros = np.zeros((3, 4))
ones = np.ones((2, 3))
range_arr = np.arange(0, 10, 2)  # [0, 2, 4, 6, 8]
linspace = np.linspace(0, 1, 5)  # [0, 0.25, 0.5, 0.75, 1]

print(f"1D array: {arr1d}")
print(f"2D array:\n{arr2d}")
print(f"Array shape: {arr2d.shape}")
print(f"Array dtype: {arr1d.dtype}")

# Array operations
print(f"Sum: {np.sum(arr1d)}")
print(f"Mean: {np.mean(arr1d)}")
print(f"Standard deviation: {np.std(arr1d)}")
print(f"Max: {np.max(arr1d)}")
print(f"Min: {np.min(arr1d)}")
```

**Array Manipulation and Mathematical Operations:**

```python
# Mathematical operations
a = np.array([1, 2, 3, 4])
b = np.array([5, 6, 7, 8])

print(f"Addition: {a + b}")
print(f"Multiplication: {a * b}")
print(f"Power: {a ** 2}")
print(f"Square root: {np.sqrt(a)}")

# Matrix operations
matrix_a = np.array([[1, 2], [3, 4]])
matrix_b = np.array([[5, 6], [7, 8]])

print(f"Matrix multiplication:\n{np.dot(matrix_a, matrix_b)}")
print(f"Element-wise multiplication:\n{matrix_a * matrix_b}")

# Array indexing and slicing
data = np.array([[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12]])
print(f"Element at [1,2]: {data[1, 2]}")
print(f"First row: {data[0, :]}")
print(f"Last column: {data[:, -1]}")
print(f"Subarray:\n{data[1:, 1:3]}")

# Boolean indexing
numbers = np.array([1, 5, 3, 8, 2, 9, 4])
mask = numbers > 4
print(f"Numbers > 4: {numbers[mask]}")
```

#### Pandas for Data Manipulation

Pandas provides powerful data structures and analysis tools for working with structured data.

**DataFrames and Series:**

```python
import pandas as pd
import numpy as np

# Creating DataFrames
data = {
    "Name": ["Alice", "Bob", "Charlie", "Diana", "Eve"],
    "Age": [25, 30, 35, 28, 32],
    "City": ["New York", "London", "Tokyo", "Paris", "Sydney"],
    "Salary": [70000, 80000, 90000, 75000, 85000]
}

df = pd.DataFrame(data)
print("DataFrame:")
print(df)
print(f"\nDataFrame info:")
print(df.info())

# Basic operations
print(f"\nFirst 3 rows:")
print(df.head(3))
print(f"\nDescriptive statistics:")
print(df.describe())

# Selecting data
print(f"\nNames column:")
print(df["Name"])
print(f"\nMultiple columns:")
print(df[["Name", "Salary"]])
print(f"\nRows where Age > 30:")
print(df[df["Age"] > 30])
```

**Data Analysis and Manipulation:**

```python
# Adding new columns
df["Salary_USD"] = df["Salary"]
df["Age_Group"] = df["Age"].apply(lambda x: "Young" if x < 30 else "Experienced")
df["Bonus"] = df["Salary"] * 0.1

print("DataFrame with new columns:")
print(df)

# Grouping and aggregation
age_groups = df.groupby("Age_Group").agg({
    "Salary": ["mean", "min", "max"],
    "Age": "mean"
})
print(f"\nGrouped data:")
print(age_groups)

# Sorting
sorted_df = df.sort_values("Salary", ascending=False)
print(f"\nSorted by salary (descending):")
print(sorted_df[["Name", "Salary"]])

# Working with missing data
df_with_na = df.copy()
df_with_na.loc[2, "Salary"] = np.nan
df_with_na.loc[4, "City"] = np.nan

print(f"\nDataFrame with missing values:")
print(df_with_na)
print(f"\nMissing values count:")
print(df_with_na.isnull().sum())

# Fill missing values
df_filled = df_with_na.fillna({
    "Salary": df_with_na["Salary"].mean(),
    "City": "Unknown"
})
print(f"\nDataFrame with filled values:")
print(df_filled)
```

#### Requests for HTTP Operations

The requests library simplifies HTTP operations for web APIs and web scraping.

**Basic HTTP Requests:**

```python
import requests
import json

# GET request
def make_get_request():
    """Demonstrate GET requests."""
    try:
        # Simple GET request
        response = requests.get("https://httpbin.org/get")
        print(f"Status code: {response.status_code}")
        print(f"Response headers: {dict(response.headers)}")
        
        # GET with parameters
        params = {"key1": "value1", "key2": "value2"}
        response = requests.get("https://httpbin.org/get", params=params)
        data = response.json()
        print(f"URL with params: {data['url']}")
        
        return response.status_code == 200
    
    except requests.exceptions.RequestException as e:
        print(f"Request failed: {e}")
        return False

# POST request
def make_post_request():
    """Demonstrate POST requests."""
    try:
        # POST with JSON data
        post_data = {
            "name": "Alice",
            "age": 30,
            "city": "New York"
        }
        
        response = requests.post(
            "https://httpbin.org/post",
            json=post_data,
            headers={"Content-Type": "application/json"}
        )
        
        if response.status_code == 200:
            result = response.json()
            print("POST request successful")
            print(f"Sent data: {result['json']}")
            return True
        else:
            print(f"POST failed with status: {response.status_code}")
            return False
    
    except requests.exceptions.RequestException as e:
        print(f"POST request failed: {e}")
        return False

# Working with APIs
def work_with_api():
    """Demonstrate working with a real API."""
    try:
        # GitHub API example
        username = "octocat"
        url = f"https://api.github.com/users/{username}"
        
        response = requests.get(url)
        
        if response.status_code == 200:
            user_data = response.json()
            print(f"GitHub user: {user_data['name']}")
            print(f"Public repos: {user_data['public_repos']}")
            print(f"Followers: {user_data['followers']}")
            print(f"Created: {user_data['created_at']}")
        else:
            print(f"Failed to fetch user data: {response.status_code}")
    
    except requests.exceptions.RequestException as e:
        print(f"API request failed: {e}")

# Session management
def session_example():
    """Demonstrate session management."""
    session = requests.Session()
    
    # Set default headers for all requests in this session
    session.headers.update({"User-Agent": "Python-Requests-Example"})
    
    try:
        # Multiple requests using the same session
        response1 = session.get("https://httpbin.org/get")
        response2 = session.get("https://httpbin.org/headers")
        
        print("Session requests completed")
        print(f"User-Agent in headers: {response2.json()['headers']['User-Agent']}")
    
    except requests.exceptions.RequestException as e:
        print(f"Session request failed: {e}")
    finally:
        session.close()

# Run HTTP examples
print("=== HTTP Requests Examples ===")
make_get_request()
make_post_request()
work_with_api()
session_example()
```

#### Matplotlib for Data Visualization

Matplotlib is the primary plotting library for creating static, animated, and interactive visualizations.

**Basic Plotting:**

```python
import matplotlib.pyplot as plt
import numpy as np

# Simple line plot
x = np.linspace(0, 10, 100)
y = np.sin(x)

plt.figure(figsize=(10, 6))
plt.plot(x, y, label='sin(x)')
plt.plot(x, np.cos(x), label='cos(x)')
plt.xlabel('X values')
plt.ylabel('Y values')
plt.title('Sine and Cosine Functions')
plt.legend()
plt.grid(True)
plt.show()

# Multiple subplots
fig, axes = plt.subplots(2, 2, figsize=(12, 8))

# Subplot 1: Line plot
axes[0, 0].plot(x, y)
axes[0, 0].set_title('Line Plot')

# Subplot 2: Scatter plot
axes[0, 1].scatter(np.random.randn(50), np.random.randn(50))
axes[0, 1].set_title('Scatter Plot')

# Subplot 3: Bar plot
categories = ['A', 'B', 'C', 'D']
values = [23, 45, 56, 78]
axes[1, 0].bar(categories, values)
axes[1, 0].set_title('Bar Plot')

# Subplot 4: Histogram
data = np.random.normal(0, 1, 1000)
axes[1, 1].hist(data, bins=30)
axes[1, 1].set_title('Histogram')

plt.tight_layout()
plt.show()
```

#### Web Frameworks

**Flask - Lightweight Web Framework:**

```python
# Basic Flask application
from flask import Flask, request, jsonify

app = Flask(__name__)

# Sample data
users = [
    {"id": 1, "name": "Alice", "email": "alice@example.com"},
    {"id": 2, "name": "Bob", "email": "bob@example.com"}
]

@app.route('/')
def home():
    return "Welcome to the Flask API!"

@app.route('/users', methods=['GET'])
def get_users():
    return jsonify(users)

@app.route('/users/<int:user_id>', methods=['GET'])
def get_user(user_id):
    user = next((u for u in users if u["id"] == user_id), None)
    if user:
        return jsonify(user)
    return jsonify({"error": "User not found"}), 404

@app.route('/users', methods=['POST'])
def create_user():
    data = request.get_json()
    new_user = {
        "id": len(users) + 1,
        "name": data.get("name"),
        "email": data.get("email")
    }
    users.append(new_user)
    return jsonify(new_user), 201

if __name__ == '__main__':
    app.run(debug=True)
```

#### Database Connectivity

**SQLite Database Operations:**

```python
import sqlite3
import pandas as pd
from datetime import datetime

def database_operations():
    """Demonstrate database operations with SQLite."""
    
    # Connect to database (creates if doesn't exist)
    conn = sqlite3.connect('example.db')
    cursor = conn.cursor()
    
    try:
        # Create table
        cursor.execute('''
            CREATE TABLE IF NOT EXISTS employees (
                id INTEGER PRIMARY KEY AUTOINCREMENT,
                name TEXT NOT NULL,
                department TEXT NOT NULL,
                salary REAL NOT NULL,
                hire_date TEXT NOT NULL
            )
        ''')
        
        # Insert data
        employees_data = [
            ("Alice Johnson", "Engineering", 75000, "2022-01-15"),
            ("Bob Smith", "Marketing", 55000, "2022-03-01"),
            ("Charlie Brown", "Engineering", 85000, "2021-06-10"),
            ("Diana Prince", "HR", 60000, "2022-02-20")
        ]
        
        cursor.executemany(
            "INSERT INTO employees (name, department, salary, hire_date) VALUES (?, ?, ?, ?)",
            employees_data
        )
        
        # Query data
        cursor.execute("SELECT * FROM employees WHERE department = ?", ("Engineering",))
        engineering_employees = cursor.fetchall()
        
        print("Engineering employees:")
        for emp in engineering_employees:
            print(f"  {emp[1]} - ${emp[3]:,}")
        
        # Using pandas with SQLite
        df = pd.read_sql_query("SELECT * FROM employees", conn)
        print(f"\nAll employees DataFrame:")
        print(df)
        
        # Aggregate queries
        cursor.execute("""
            SELECT department, COUNT(*) as count, AVG(salary) as avg_salary
            FROM employees
            GROUP BY department
        """)
        
        dept_stats = cursor.fetchall()
        print(f"\nDepartment statistics:")
        for dept, count, avg_sal in dept_stats:
            print(f"  {dept}: {count} employees, avg salary: ${avg_sal:,.2f}")
        
        conn.commit()
        
    except sqlite3.Error as e:
        print(f"Database error: {e}")
        conn.rollback()
    
    finally:
        conn.close()

# Run database operations
database_operations()
```

**Key Takeaways:**

- NumPy provides efficient array operations and mathematical functions
- Pandas excels at data manipulation and analysis with DataFrames
- Requests simplifies HTTP operations and API interactions
- Matplotlib creates comprehensive data visualizations
- Flask enables rapid web application development
- SQLite provides lightweight database functionality
- These libraries form the foundation of most Python data science and web development projects

### Best Practices

#### PEP 8 Style Guide

PEP 8 is the official style guide for Python code, ensuring consistency and readability across projects.

**Naming Conventions:**

```python
# Variables and functions: lowercase with underscores
user_name = "alice"
total_count = 100

def calculate_total_price(item_price, tax_rate):
    """Calculate total price including tax."""
    return item_price * (1 + tax_rate)

# Constants: uppercase with underscores
MAX_CONNECTIONS = 100
DEFAULT_TIMEOUT = 30
PI = 3.14159

# Classes: PascalCase
class UserAccount:
    """Represents a user account."""
    
    def __init__(self, username):
        self.username = username
        self._balance = 0  # Protected attribute
        self.__account_id = self._generate_id()  # Private attribute
    
    def _generate_id(self):
        """Protected method for internal use."""
        import random
        return random.randint(10000, 99999)

# Modules and packages: lowercase with underscores
# file_utils.py, data_processor.py
```

**Code Layout and Formatting:**

```python
# Imports: standard library, third-party, local imports
import os
import sys
from datetime import datetime

import requests
import pandas as pd

from my_package import my_module
from . import local_module

# Line length: maximum 79 characters
def long_function_name(
    parameter_one, parameter_two, parameter_three,
    parameter_four, parameter_five, parameter_six
):
    """Function with many parameters."""
    return parameter_one + parameter_two

# Whitespace in expressions
# Good
spam(ham[1], {eggs: 2})
if x == 4:
    print(x, y)
x, y = y, x

# Bad examples (don't do this):
# spam( ham[ 1 ], { eggs : 2 } )
# if x == 4 : print x , y ; x , y = y , x

# Blank lines
class MyClass:
    """Example class demonstrating blank line usage."""
    
    def __init__(self):
        self.value = 0
    
    def method_one(self):
        """First method."""
        return self.value
    
    def method_two(self):
        """Second method."""
        return self.value * 2


def standalone_function():
    """Standalone function with proper spacing."""
    pass
```

**Documentation and Comments:**

```python
def calculate_compound_interest(principal, rate, time, compound_frequency=1):
    """
    Calculate compound interest.
    
    Args:
        principal (float): Initial amount of money
        rate (float): Annual interest rate (as decimal, e.g., 0.05 for 5%)
        time (float): Time period in years
        compound_frequency (int): Number of times interest compounds per year
    
    Returns:
        float: Final amount after compound interest
    
    Raises:
        ValueError: If any parameter is negative
    
    Example:
        >>> calculate_compound_interest(1000, 0.05, 2, 4)
        1104.89
    """
    if any(param < 0 for param in [principal, rate, time, compound_frequency]):
        raise ValueError("All parameters must be non-negative")
    
    # Formula: A = P(1 + r/n)^(nt)
    amount = principal * (1 + rate / compound_frequency) ** (compound_frequency * time)
    return round(amount, 2)

# Inline comments should be used sparingly
x = x + 1  # Increment x by 1

# Block comments explain the following code
# The following loop processes each user in the database
# and updates their last_login timestamp
for user in users:
    user.update_last_login()
```

#### Code Organization

**Project Structure:**

```
my_project/
├── README.md
├── requirements.txt
├── setup.py
├── .gitignore
├── .env.example
├── my_project/
│   ├── __init__.py
│   ├── main.py
│   ├── config.py
│   ├── models/
│   │   ├── __init__.py
│   │   ├── user.py
│   │   └── product.py
│   ├── services/
│   │   ├── __init__.py
│   │   ├── user_service.py
│   │   └── email_service.py
│   └── utils/
│       ├── __init__.py
│       ├── helpers.py
│       └── validators.py
├── tests/
│   ├── __init__.py
│   ├── test_models.py
│   ├── test_services.py
│   └── fixtures/
│       └── sample_data.json
└── docs/
    ├── api.md
    └── deployment.md
```

**Configuration Management:**

```python
# config.py - Centralized configuration
import os
from dataclasses import dataclass
from typing import Optional

@dataclass
class DatabaseConfig:
    """Database configuration."""
    host: str = "localhost"
    port: int = 5432
    name: str = "myapp"
    user: str = "user"
    password: str = "password"

@dataclass
class AppConfig:
    """Application configuration."""
    debug: bool = False
    secret_key: str = "your-secret-key"
    database: DatabaseConfig = DatabaseConfig()
    
    @classmethod
    def from_env(cls) -> 'AppConfig':
        """Create config from environment variables."""
        return cls(
            debug=os.getenv('DEBUG', 'False').lower() == 'true',
            secret_key=os.getenv('SECRET_KEY', 'default-secret'),
            database=DatabaseConfig(
                host=os.getenv('DB_HOST', 'localhost'),
                port=int(os.getenv('DB_PORT', '5432')),
                name=os.getenv('DB_NAME', 'myapp'),
                user=os.getenv('DB_USER', 'user'),
                password=os.getenv('DB_PASSWORD', 'password')
            )
        )

# Usage
config = AppConfig.from_env()
```

**Error Handling Patterns:**

```python
# Custom exception hierarchy
class AppError(Exception):
    """Base application exception."""
    pass

class ValidationError(AppError):
    """Raised when data validation fails."""
    pass

class DatabaseError(AppError):
    """Raised when database operations fail."""
    pass

# Service layer with proper error handling
class UserService:
    """Service for user operations."""
    
    def __init__(self, database):
        self.database = database
    
    def create_user(self, user_data):
        """Create a new user with validation."""
        try:
            # Validate input
            self._validate_user_data(user_data)
            
            # Check if user exists
            if self._user_exists(user_data['email']):
                raise ValidationError(f"User with email {user_data['email']} already exists")
            
            # Create user
            user = self.database.create_user(user_data)
            return user
        
        except ValidationError:
            raise  # Re-raise validation errors
        except Exception as e:
            raise DatabaseError(f"Failed to create user: {str(e)}") from e
    
    def _validate_user_data(self, data):
        """Validate user data."""
        required_fields = ['name', 'email', 'password']
        for field in required_fields:
            if field not in data or not data[field]:
                raise ValidationError(f"Missing required field: {field}")
        
        if '@' not in data['email']:
            raise ValidationError("Invalid email format")
    
    def _user_exists(self, email):
        """Check if user exists."""
        return self.database.get_user_by_email(email) is not None
```

#### Testing

**Unit Testing with unittest:**

```python
import unittest
from unittest.mock import Mock, patch
from my_project.services.user_service import UserService, ValidationError

class TestUserService(unittest.TestCase):
    """Test cases for UserService."""
    
    def setUp(self):
        """Set up test fixtures."""
        self.mock_database = Mock()
        self.user_service = UserService(self.mock_database)
        self.valid_user_data = {
            'name': 'John Doe',
            'email': 'john@example.com',
            'password': 'secure123'
        }
    
    def test_create_user_success(self):
        """Test successful user creation."""
        # Arrange
        self.mock_database.get_user_by_email.return_value = None
        self.mock_database.create_user.return_value = {'id': 1, **self.valid_user_data}
        
        # Act
        result = self.user_service.create_user(self.valid_user_data)
        
        # Assert
        self.assertEqual(result['id'], 1)
        self.mock_database.create_user.assert_called_once_with(self.valid_user_data)
    
    def test_create_user_missing_field(self):
        """Test user creation with missing required field."""
        # Arrange
        invalid_data = {'name': 'John Doe', 'email': 'john@example.com'}
        
        # Act & Assert
        with self.assertRaises(ValidationError) as context:
            self.user_service.create_user(invalid_data)
        
        self.assertIn('Missing required field: password', str(context.exception))
    
    def test_create_user_invalid_email(self):
        """Test user creation with invalid email."""
        # Arrange
        invalid_data = {**self.valid_user_data, 'email': 'invalid-email'}
        
        # Act & Assert
        with self.assertRaises(ValidationError) as context:
            self.user_service.create_user(invalid_data)
        
        self.assertIn('Invalid email format', str(context.exception))
    
    def test_create_user_already_exists(self):
        """Test user creation when user already exists."""
        # Arrange
        self.mock_database.get_user_by_email.return_value = {'id': 1}
        
        # Act & Assert
        with self.assertRaises(ValidationError) as context:
            self.user_service.create_user(self.valid_user_data)
        
        self.assertIn('already exists', str(context.exception))

if __name__ == '__main__':
    unittest.main()
```

**Testing with pytest:**

```python
import pytest
from unittest.mock import Mock
from my_project.services.user_service import UserService, ValidationError

class TestUserServicePytest:
    """Test UserService using pytest."""
    
    @pytest.fixture
    def mock_database(self):
        """Mock database fixture."""
        return Mock()
    
    @pytest.fixture
    def user_service(self, mock_database):
        """UserService fixture."""
        return UserService(mock_database)
    
    @pytest.fixture
    def valid_user_data(self):
        """Valid user data fixture."""
        return {
            'name': 'John Doe',
            'email': 'john@example.com',
            'password': 'secure123'
        }
    
    def test_create_user_success(self, user_service, mock_database, valid_user_data):
        """Test successful user creation."""
        # Arrange
        mock_database.get_user_by_email.return_value = None
        mock_database.create_user.return_value = {'id': 1, **valid_user_data}
        
        # Act
        result = user_service.create_user(valid_user_data)
        
        # Assert
        assert result['id'] == 1
        mock_database.create_user.assert_called_once_with(valid_user_data)
    
    @pytest.mark.parametrize("missing_field", ["name", "email", "password"])
    def test_create_user_missing_fields(self, user_service, valid_user_data, missing_field):
        """Test user creation with missing fields."""
        # Arrange
        invalid_data = valid_user_data.copy()
        del invalid_data[missing_field]
        
        # Act & Assert
        with pytest.raises(ValidationError, match=f"Missing required field: {missing_field}"):
            user_service.create_user(invalid_data)
    
    def test_create_user_invalid_email(self, user_service, valid_user_data):
        """Test user creation with invalid email."""
        # Arrange
        valid_user_data['email'] = 'invalid-email'
        
        # Act & Assert
        with pytest.raises(ValidationError, match="Invalid email format"):
            user_service.create_user(valid_user_data)
```

#### Version Control with Git

**Git Best Practices:**

```bash
# Initialize repository
git init
git add .
git commit -m "Initial commit"

# Branching strategy
git checkout -b feature/user-authentication
git checkout -b bugfix/login-error
git checkout -b hotfix/security-patch

# Commit message conventions
git commit -m "feat: add user authentication system"
git commit -m "fix: resolve login timeout issue"
git commit -m "docs: update API documentation"
git commit -m "refactor: improve database connection handling"
git commit -m "test: add unit tests for user service"

# .gitignore for Python projects
__pycache__/
*.py[cod]
*$py.class
*.so
.Python
build/
develop-eggs/
dist/
downloads/
eggs/
.eggs/
lib/
lib64/
parts/
sdist/
var/
wheels/
*.egg-info/
.installed.cfg
*.egg

# Virtual environments
venv/
env/
ENV/

# IDE files
.vscode/
.idea/
*.swp
*.swo

# Environment variables
.env
.env.local

# Database
*.db
*.sqlite3

# Logs
*.log
logs/
```

#### Performance Optimization

**Code Optimization Techniques:**

```python
import time
import cProfile
from functools import lru_cache
from collections import defaultdict

# Timing decorator
def timer(func):
    """Decorator to measure function execution time."""
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"{func.__name__} took {end - start:.4f} seconds")
        return result
    return wrapper

# Memoization for expensive calculations
@lru_cache(maxsize=128)
def fibonacci(n):
    """Fibonacci with memoization."""
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

# Efficient data structures
def count_words_efficient(text):
    """Count words using defaultdict."""
    word_count = defaultdict(int)
    for word in text.split():
        word_count[word.lower()] += 1
    return dict(word_count)

# List comprehensions vs loops
@timer
def squares_loop(n):
    """Calculate squares using loop."""
    result = []
    for i in range(n):
        result.append(i ** 2)
    return result

@timer
def squares_comprehension(n):
    """Calculate squares using list comprehension."""
    return [i ** 2 for i in range(n)]

# Generator for memory efficiency
def read_large_file_generator(filename):
    """Read large file line by line using generator."""
    with open(filename, 'r') as file:
        for line in file:
            yield line.strip()

# Profiling code
def profile_function():
    """Example function to profile."""
    data = list(range(100000))
    result = sum(x ** 2 for x in data if x % 2 == 0)
    return result

# Run profiling
if __name__ == "__main__":
    cProfile.run('profile_function()')
```

#### Logging and Debugging

**Comprehensive Logging Setup:**

```python
import logging
import logging.config
from datetime import datetime

# Logging configuration
LOGGING_CONFIG = {
    'version': 1,
    'disable_existing_loggers': False,
    'formatters': {
        'standard': {
            'format': '%(asctime)s [%(levelname)s] %(name)s: %(message)s'
        },
        'detailed': {
            'format': '%(asctime)s [%(levelname)s] %(name)s:%(lineno)d: %(message)s'
        },
    },
    'handlers': {
        'console': {
            'level': 'INFO',
            'class': 'logging.StreamHandler',
            'formatter': 'standard',
        },
        'file': {
            'level': 'DEBUG',
            'class': 'logging.FileHandler',
            'filename': 'app.log',
            'formatter': 'detailed',
        },
    },
    'loggers': {
        '': {  # root logger
            'handlers': ['console', 'file'],
            'level': 'DEBUG',
            'propagate': False
        }
    }
}

# Configure logging
logging.config.dictConfig(LOGGING_CONFIG)
logger = logging.getLogger(__name__)

# Example usage
class DatabaseManager:
    """Example class with comprehensive logging."""
    
    def __init__(self):
        self.logger = logging.getLogger(self.__class__.__name__)
        self.connection = None
    
    def connect(self, connection_string):
        """Connect to database with logging."""
        try:
            self.logger.info(f"Attempting to connect to database")
            # Simulate connection
            self.connection = f"Connected to {connection_string}"
            self.logger.info("Database connection successful")
            return True
        except Exception as e:
            self.logger.error(f"Database connection failed: {e}")
            return False
    
    def execute_query(self, query):
        """Execute query with logging."""
        if not self.connection:
            self.logger.warning("No database connection available")
            return None
        
        self.logger.debug(f"Executing query: {query}")
        try:
            # Simulate query execution
            result = f"Result for: {query}"
            self.logger.info(f"Query executed successfully, returned {len(result)} characters")
            return result
        except Exception as e:
            self.logger.error(f"Query execution failed: {e}")
            return None

# Usage example
db = DatabaseManager()
db.connect("postgresql://localhost:5432/mydb")
db.execute_query("SELECT * FROM users")
```

**Key Takeaways:**

- Follow PEP 8 for consistent, readable code
- Organize projects with clear structure and separation of concerns
- Write comprehensive tests using unittest or pytest
- Use version control effectively with meaningful commit messages
- Optimize performance with appropriate data structures and algorithms
- Implement proper logging for debugging and monitoring
- Handle errors gracefully with custom exception hierarchies
- Document code thoroughly with docstrings and comments

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

## Quick Reference Cheat Sheet

### Essential Python Syntax

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

### Common Built-in Functions

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

### String Methods Quick Reference

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

### List Methods Quick Reference

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

### Dictionary Methods Quick Reference

```python
d = {"a": 1, "b": 2}
d.keys()               # dict_keys(['a', 'b'])
d.values()             # dict_values([1, 2])
d.items()              # dict_items([('a', 1), ('b', 2)])
d.get("c", 0)          # Get with default: 0
d.pop("a")             # Remove and return: 1
d.update({"c": 3})     # Add/update: {"b": 2, "c": 3}
```

## Navigation Guide

### Learning Path Recommendations

**Complete Beginner (0-2 months):**
1. [Getting Started](#getting-started) - Set up your environment
2. [Basic Syntax](#basic-syntax) - Learn variables and code structure
3. [Data Types](#data-types) - Master strings, numbers, lists, dictionaries
4. [Operators](#operators) - Understand arithmetic and logical operations
5. [Input and Output](#input-and-output) - Interact with users
6. Practice with simple projects from [Practice Exercises](#practice-exercises)

**Intermediate Developer (2-6 months):**
1. [Control Structures](#control-structures) - Master if/else, loops
2. [Functions](#functions) - Write reusable code
3. [Error Handling](#error-handling) - Handle exceptions gracefully
4. [Modules and Packages](#modules-and-packages) - Organize your code
5. Build projects from [Project Ideas](#project-ideas)

**Advanced Programmer (6-12 months):**
1. [Object-Oriented Programming](#object-oriented-programming) - Classes and inheritance
2. [Advanced Features](#advanced-features) - Decorators, generators, context managers
3. [File Handling](#file-handling) - Work with files and data
4. Explore [Popular Libraries](#popular-libraries)

**Professional Developer (12+ months):**
1. [Best Practices](#best-practices) - Write production-quality code
2. [Testing](#testing) - Ensure code reliability
3. [Performance Optimization](#performance-optimization) - Make code efficient
4. Contribute to open source projects

### Cross-References

**When learning about Variables ([Basic Syntax](#basic-syntax)), also see:**
- [Data Types](#data-types) for what you can store in variables
- [Operators](#operators) for what you can do with variables
- [Functions](#functions) for variable scope concepts

**When learning about Lists ([Data Types](#data-types)), also see:**
- [Control Structures](#control-structures) for iterating over lists
- [List Comprehensions](#list-comprehensions) for advanced list creation
- [Functions](#functions) for passing lists as arguments

**When learning about Functions ([Functions](#functions)), also see:**
- [Error Handling](#error-handling) for handling function errors
- [Decorators](#decorators) for modifying function behavior
- [Testing](#testing) for testing your functions

**When learning about Classes ([Object-Oriented Programming](#object-oriented-programming)), also see:**
- [Special Methods](#special-methods) for customizing class behavior
- [Inheritance](#inheritance) for code reuse
- [Best Practices](#best-practices) for class design patterns

**When working with Files ([File Handling](#file-handling)), also see:**
- [Error Handling](#error-handling) for handling file errors
- [Context Managers](#context-managers) for proper resource management
- [Pathlib](#file-paths-with-pathlib) for modern path handling

### Troubleshooting Cross-References

**Common Error Types and Where to Learn More:**
- `SyntaxError` → [Basic Syntax](#basic-syntax)
- `NameError` → [Variables and Naming](#variables-and-naming)
- `TypeError` → [Data Types](#data-types)
- `IndexError` → [Lists](#lists) and [Error Handling](#error-handling)
- `KeyError` → [Dictionaries](#dictionaries) and [Error Handling](#error-handling)
- `FileNotFoundError` → [File Handling](#file-handling)
- `ImportError` → [Modules and Packages](#modules-and-packages)

### Related Concepts Map

```
Basic Syntax
├── Variables → Data Types → Operators
├── Comments → Documentation → Best Practices
└── Indentation → Control Structures → Functions

Data Types
├── Strings → String Methods → Text Processing
├── Lists → List Methods → Iteration → Comprehensions
├── Dictionaries → JSON → Data Storage
└── Numbers → Mathematical Operations → NumPy

Control Structures
├── If/Else → Boolean Logic → Operators
├── Loops → Iteration → Generators
└── Break/Continue → Flow Control → Functions

Functions
├── Parameters → Arguments → Scope
├── Return Values → Error Handling
├── Lambda → Functional Programming
└── Decorators → Advanced Features

Object-Oriented Programming
├── Classes → Objects → Inheritance
├── Methods → Functions → Encapsulation
└── Properties → Descriptors → Metaclasses

Advanced Features
├── Decorators → Functions → Metaprogramming
├── Generators → Iteration → Memory Efficiency
├── Context Managers → Resource Management → Files
└── Comprehensions → Functional Programming → Performance

File Handling
├── Text Files → Strings → Encoding
├── CSV Files → Data Analysis → Pandas
├── JSON Files → APIs → Web Development
└── Binary Files → Serialization → Databases

Professional Development
├── Testing → Quality Assurance → Debugging
├── Version Control → Collaboration → Git
├── Documentation → Communication → APIs
└── Performance → Optimization → Profiling
```

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