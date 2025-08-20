# Modules and Packages

Modules and packages help organize code into reusable components and manage larger Python projects effectively.

## Importing Modules

### Basic Import Statements

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

### Different Import Methods

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

## Creating Custom Modules

### Creating Your First Module

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

### Using Your Custom Module

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

## Package Structure

### Creating a Package

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

### Using Your Package

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

## Standard Library Overview

### Essential Standard Library Modules

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

## Virtual Environments

### Creating and Using Virtual Environments

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

### Managing Dependencies

Create a `requirements.txt` file:

```txt
requests==2.28.1
pandas==1.5.2
numpy==1.24.1
matplotlib==3.6.2
```

### Virtual Environment Best Practices

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

## Module Search Path

### Understanding Python's Import System

```python
import sys

# View Python's module search path
print("Python module search path:")
for path in sys.path:
    print(f"  {path}")

# Add custom path to module search
sys.path.append('/path/to/my/modules')

# Check if module can be imported
def can_import(module_name):
    """Check if a module can be imported."""
    try:
        __import__(module_name)
        return True
    except ImportError:
        return False

print(f"Can import 'requests': {can_import('requests')}")
print(f"Can import 'my_custom_module': {can_import('my_custom_module')}")
```

## Package Distribution

### Creating a Distributable Package

Create a `setup.py` file:

```python
# setup.py
from setuptools import setup, find_packages

setup(
    name="my-python-package",
    version="1.0.0",
    author="Your Name",
    author_email="your.email@example.com",
    description="A sample Python package",
    long_description=open("README.md").read(),
    long_description_content_type="text/markdown",
    url="https://github.com/yourusername/my-python-package",
    packages=find_packages(),
    classifiers=[
        "Development Status :: 3 - Alpha",
        "Intended Audience :: Developers",
        "License :: OSI Approved :: MIT License",
        "Programming Language :: Python :: 3",
        "Programming Language :: Python :: 3.8",
        "Programming Language :: Python :: 3.9",
        "Programming Language :: Python :: 3.10",
    ],
    python_requires=">=3.8",
    install_requires=[
        "requests>=2.25.0",
        "numpy>=1.20.0",
    ],
    extras_require={
        "dev": [
            "pytest>=6.0",
            "black>=21.0",
            "flake8>=3.8",
        ],
    },
)
```

### Building and Installing Your Package

```bash
# Build the package
python setup.py sdist bdist_wheel

# Install locally in development mode
pip install -e .

# Install from built package
pip install dist/my-python-package-1.0.0.tar.gz

# Upload to PyPI (requires account)
pip install twine
twine upload dist/*
```

## Practice Exercise - Project Structure

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

## Key Takeaways

- Use `import` statements to access code from other modules
- Create custom modules by writing `.py` files with functions and classes
- Organize related modules into packages using `__init__.py` files
- The standard library provides many useful modules for common tasks
- Virtual environments isolate project dependencies
- Proper project structure makes code maintainable and shareable
- Use `if __name__ == "__main__":` to make modules both importable and executable

## What's Next?

Now that you understand modules and packages, you're ready to dive into object-oriented programming concepts. Let's move on to [Object-Oriented Programming](10-oop.md)!