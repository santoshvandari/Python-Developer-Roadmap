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

## Intermediate Level

_This section will be implemented in subsequent tasks_

## Advanced Level

_This section will be implemented in subsequent tasks_

## Professional Level

_This section will be implemented in subsequent tasks_

## Resources and Next Steps

_This section will be implemented in subsequent tasks_

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
