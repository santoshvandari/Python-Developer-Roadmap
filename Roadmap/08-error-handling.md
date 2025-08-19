# Error Handling

Error handling allows your programs to gracefully handle unexpected situations and continue running or fail gracefully.

## Try/Except Blocks

### Basic Exception Handling

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

## Common Exception Types

### Built-in Exception Types

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

# AttributeError - attribute doesn't exist
try:
    text = "hello"
    text.nonexistent_method()
except AttributeError as e:
    print(f"AttributeError: {e}")
```

## Finally Blocks

### Using Finally for Cleanup

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

## Custom Exceptions

### Creating Custom Exception Classes

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

## Debugging Techniques

### Debugging Strategies

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

## Error Handling Patterns

### Defensive Programming

```python
def safe_divide(a, b):
    """Safely divide two numbers with comprehensive error handling."""
    
    # Input validation
    if not isinstance(a, (int, float)):
        raise TypeError(f"First argument must be a number, got {type(a)}")
    if not isinstance(b, (int, float)):
        raise TypeError(f"Second argument must be a number, got {type(b)}")
    
    # Business logic validation
    if b == 0:
        raise ZeroDivisionError("Cannot divide by zero")
    
    # Perform operation
    try:
        result = a / b
        return result
    except Exception as e:
        # Log unexpected errors
        logging.error(f"Unexpected error in safe_divide: {e}")
        raise

def robust_file_reader(filename, encoding='utf-8'):
    """Read a file with comprehensive error handling."""
    
    if not isinstance(filename, str):
        raise TypeError("Filename must be a string")
    
    if not filename.strip():
        raise ValueError("Filename cannot be empty")
    
    try:
        with open(filename, 'r', encoding=encoding) as file:
            content = file.read()
            return content
    except FileNotFoundError:
        raise FileNotFoundError(f"File '{filename}' not found")
    except PermissionError:
        raise PermissionError(f"Permission denied to read '{filename}'")
    except UnicodeDecodeError as e:
        raise UnicodeDecodeError(
            e.encoding, e.object, e.start, e.end,
            f"Cannot decode file '{filename}' with {encoding} encoding"
        )
    except Exception as e:
        logging.error(f"Unexpected error reading '{filename}': {e}")
        raise
```

### Error Recovery Strategies

```python
def retry_operation(operation, max_attempts=3, delay=1):
    """Retry an operation with exponential backoff."""
    import time
    
    for attempt in range(max_attempts):
        try:
            return operation()
        except Exception as e:
            if attempt == max_attempts - 1:
                # Last attempt failed, re-raise the exception
                raise
            
            print(f"Attempt {attempt + 1} failed: {e}")
            print(f"Retrying in {delay} seconds...")
            time.sleep(delay)
            delay *= 2  # Exponential backoff

# Example usage
def unreliable_network_call():
    import random
    if random.random() < 0.7:  # 70% chance of failure
        raise ConnectionError("Network timeout")
    return "Success!"

try:
    result = retry_operation(unreliable_network_call, max_attempts=5)
    print(f"Operation succeeded: {result}")
except Exception as e:
    print(f"Operation failed after all retries: {e}")
```

## Logging and Error Reporting

### Comprehensive Logging Setup

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

## Practice Exercise - Robust File Processor

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

# Example usage
def main():
    processor = FileProcessor()
    
    # Test files
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

## Key Takeaways

- Use try/except blocks to handle specific exceptions
- Always handle the most specific exceptions first
- Use finally blocks for cleanup operations
- Create custom exceptions for domain-specific errors
- Log errors for debugging and monitoring
- Use assert statements for debugging assumptions
- Handle exceptions at the appropriate level in your code
- Don't catch exceptions you can't handle meaningfully

## What's Next?

Now that you understand error handling, you're ready to learn about organizing your code into modules and packages. Let's move on to [Modules and Packages](09-modules-packages.md)!