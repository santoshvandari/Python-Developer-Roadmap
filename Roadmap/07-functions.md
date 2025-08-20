# Functions

Functions are reusable blocks of code that perform specific tasks. They help organize code, reduce repetition, and make programs more modular.

## Function Definition

### Basic Function Syntax

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

## Parameters and Arguments

### Different Types of Parameters

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

### Variable-Length Arguments

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

## Return Values

### Basic Return Statements

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

### Early Returns and Guard Clauses

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

## Variable Scope

### Local vs Global Scope

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

## Lambda Functions

### Basic Lambda Functions

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

## Function Documentation

### Docstrings and Type Hints

```python
def calculate_area(length: float, width: float) -> float:
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

# Function annotations
def process_data(data: list, multiplier: float = 1.0) -> list:
    """Process data by multiplying each element."""
    return [item * multiplier for item in data]
```

## Higher-Order Functions

### Functions as Arguments

```python
def apply_operation(numbers, operation):
    """Apply an operation to a list of numbers."""
    return [operation(num) for num in numbers]

def square(x):
    return x ** 2

def cube(x):
    return x ** 3

numbers = [1, 2, 3, 4, 5]
squared_numbers = apply_operation(numbers, square)
cubed_numbers = apply_operation(numbers, cube)

print(f"Squared: {squared_numbers}")  # Output: [1, 4, 9, 16, 25]
print(f"Cubed: {cubed_numbers}")      # Output: [1, 8, 27, 64, 125]

# Using lambda with higher-order functions
doubled = apply_operation(numbers, lambda x: x * 2)
print(f"Doubled: {doubled}")  # Output: [2, 4, 6, 8, 10]
```

### Functions Returning Functions

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
```

## Decorators (Introduction)

### Basic Decorator Concept

```python
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
```

## Practice Exercise - Advanced Calculator

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

## Key Takeaways

- Functions make code reusable and organized
- Use parameters to make functions flexible
- Return values to get results from functions
- Understand scope: local, global, and nonlocal
- Lambda functions are useful for short, simple operations
- Document functions with docstrings and type hints
- Functions can be stored in variables and passed as arguments
- Use default parameters to make functions more flexible

## What's Next?

Now that you understand functions, you're ready to learn about handling errors and exceptions in your programs. Let's move on to [Error Handling](08-error-handling.md)!