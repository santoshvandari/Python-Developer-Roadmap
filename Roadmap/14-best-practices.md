# Best Practices

Professional Python development requires following established best practices for code quality, maintainability, and collaboration.

## PEP 8 Style Guide

PEP 8 is the official style guide for Python code, ensuring consistency and readability across projects.

### Naming Conventions

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

### Code Layout and Formatting

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

### Documentation and Comments

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