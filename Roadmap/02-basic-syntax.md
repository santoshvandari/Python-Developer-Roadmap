# Basic Syntax

Python's syntax is designed to be readable and straightforward. Let's start with the fundamental building blocks of Python programming.

## Variables and Naming

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

## Comments and Documentation

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

## Code Structure and Indentation

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

## Key Takeaways

- Variables don't need type declarations
- Use descriptive variable names with underscores
- Comments start with # for single lines
- Use triple quotes for multi-line comments and docstrings
- Python uses 4-space indentation to define code blocks
- Avoid using Python keywords as variable names
- Keep your code clean and well-organized

## What's Next?

Now that you understand Python's basic syntax, you're ready to learn about the different types of data you can work with. Let's move on to [Data Types](03-data-types.md)!