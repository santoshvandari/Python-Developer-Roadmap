# Advanced Features

Python offers several advanced features that enable more sophisticated programming patterns and improved code efficiency.

## Decorators

Decorators are a powerful feature that allows you to modify or extend the behavior of functions and classes.

### Function Decorators

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

### Practical Decorators

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

### Class Decorators

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

## Generators and Iterators

Generators are functions that return an iterator object, allowing you to iterate over a sequence of values without storing them all in memory.

### Basic Generators

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

### Advanced Generator Patterns

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

### Custom Iterators

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

## Context Managers

Context managers ensure proper resource management using the `with` statement.

### Built-in Context Managers

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

### Custom Context Managers

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

## Advanced Comprehensions and Functional Programming

### Advanced Comprehensions

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

### Functional Programming Features

```python
# Higher-order functions
def apply_operation(numbers, operation):
    """Apply an operation to a list of numbers."""
    return [operation(num) for num in numbers]

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

# Partial functions
from functools import partial, reduce

def power(base, exponent):
    return base ** exponent

# Create specialized functions
square = partial(power, exponent=2)
cube = partial(power, exponent=3)

print(square(5))  # Output: 25
print(cube(3))    # Output: 27

# Using map, filter, reduce
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# Map: apply function to all elements
squared = list(map(lambda x: x**2, numbers))
print(squared)  # Output: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

# Filter: select elements based on condition
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)  # Output: [2, 4, 6, 8, 10]

# Reduce: combine all elements into single value
product = reduce(lambda x, y: x * y, numbers)
print(product)  # Output: 3628800

# Combining functional operations
result = reduce(
    lambda x, y: x + y,
    map(lambda x: x**2, 
        filter(lambda x: x % 2 == 0, numbers))
)
print(result)  # Sum of squares of even numbers: 220
```

## Metaprogramming

### Dynamic Class Creation

```python
# Creating classes dynamically
def create_class(name, methods):
    """Create a class dynamically."""
    return type(name, (object,), methods)

# Create a class with methods
methods = {
    '__init__': lambda self, value: setattr(self, 'value', value),
    'get_value': lambda self: self.value,
    'set_value': lambda self, value: setattr(self, 'value', value)
}

DynamicClass = create_class('DynamicClass', methods)
obj = DynamicClass(42)
print(obj.get_value())  # Output: 42

# Metaclasses (advanced)
class SingletonMeta(type):
    """Metaclass that creates singleton instances."""
    _instances = {}
    
    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super().__call__(*args, **kwargs)
        return cls._instances[cls]

class Singleton(metaclass=SingletonMeta):
    def __init__(self, value):
        self.value = value

# Test singleton behavior
s1 = Singleton(1)
s2 = Singleton(2)
print(s1 is s2)  # Output: True
print(s1.value)  # Output: 1 (first instance value)
```

## Practice Exercise - Advanced Features Integration

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

## Key Takeaways

- Decorators modify function behavior and can be stacked for multiple effects
- Generators provide memory-efficient iteration over large datasets
- Context managers ensure proper resource management and cleanup
- List comprehensions offer concise syntax for data transformation
- Custom iterators provide fine-grained control over iteration behavior
- Closures capture variables from enclosing scopes for stateful functions
- Advanced features work together to create powerful, efficient programs

## What's Next?

Now that you understand Python's advanced features, you're ready to learn about working with files and different data formats. Let's move on to [File Handling](12-file-handling.md)!