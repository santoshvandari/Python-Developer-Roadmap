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
## Code Organization

### Project Structure

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

### Configuration Management

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

### Error Handling Patterns

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

## Testing

### Unit Testing with unittest

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

### Testing with pytest

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
```#
# Version Control with Git

### Git Best Practices

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
git commit -m "feat: add user authenticationsue"
git commit -m "docs: update API documentation"
git commit -m "refactor: improve database connection handling"
git commit -m "tes system"
git commit -m "fix: resolvnit tests for user service"

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

## Performance Optimization

### Code Optimization Techniques

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

## Logging and Debugging

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

## Documentation and Code Quality

### Type Hints and Documentation

```python
from typing import List, Dict, Optional, Union, Callable
from dataclasses import dataclass
from enum import Enum

class UserRole(Enum):
    """User role enumeration."""
    ADMIN = "admin"
    USER = "user"
    GUEST = "guest"

@dataclass
class User:
    """User data class with type hints."""
    id: int
    name: str
    email: str
    role: UserRole
    is_active: bool = True
    metadata: Optional[Dict[str, str]] = None

def process_users(
    users: List[User],
    filter_func: Callable[[User], bool],
    transform_func: Optional[Callable[[User], Dict[str, Union[str, int]]]] = None
) -> List[Dict[str, Union[str, int]]]:
    """
    Process a list of users with filtering and optional transformation.
    
    Args:
        users: List of User objects to process
        filter_func: Function to filter users
        transform_func: Optional function to transform user data
    
    Returns:
        List of processed user dictionaries
    
    Example:
        >>> users = [User(1, "Alice", "alice@example.com", UserRole.USER)]
        >>> active_users = process_users(users, lambda u: u.is_active)
        >>> len(active_users)
        1
    """
    filtered_users = [user for user in users if filter_func(user)]
    
    if transform_func:
        return [transform_func(user) for user in filtered_users]
    
    return [
        {
            "id": user.id,
            "name": user.name,
            "email": user.email,
            "role": user.role.value
        }
        for user in filtered_users
    ]

# Usage with type hints
def get_admin_users(users: List[User]) -> List[User]:
    """Get all admin users."""
    return [user for user in users if user.role == UserRole.ADMIN]
```

### Code Quality Tools

```python
# Example of well-formatted, documented code following best practices

class APIClient:
    """
    A robust API client with proper error handling and logging.
    
    This class provides a clean interface for making HTTP requests
    with automatic retry logic, proper error handling, and comprehensive logging.
    """
    
    def __init__(self, base_url: str, timeout: int = 30, max_retries: int = 3):
        """
        Initialize the API client.
        
        Args:
            base_url: The base URL for the API
            timeout: Request timeout in seconds
            max_retries: Maximum number of retry attempts
        """
        self.base_url = base_url.rstrip('/')
        self.timeout = timeout
        self.max_retries = max_retries
        self.session = self._create_session()
        self.logger = logging.getLogger(self.__class__.__name__)
    
    def _create_session(self) -> requests.Session:
        """Create and configure a requests session."""
        session = requests.Session()
        session.headers.update({
            'User-Agent': 'APIClient/1.0',
            'Accept': 'application/json',
            'Content-Type': 'application/json'
        })
        return session
    
    def get(self, endpoint: str, params: Optional[Dict[str, str]] = None) -> Dict:
        """
        Make a GET request to the specified endpoint.
        
        Args:
            endpoint: API endpoint (without base URL)
            params: Optional query parameters
        
        Returns:
            JSON response as dictionary
        
        Raises:
            APIError: If the request fails after all retries
        """
        url = f"{self.base_url}/{endpoint.lstrip('/')}"
        
        for attempt in range(self.max_retries + 1):
            try:
                self.logger.debug(f"GET request to {url}, attempt {attempt + 1}")
                response = self.session.get(url, params=params, timeout=self.timeout)
                response.raise_for_status()
                
                self.logger.info(f"Successful GET request to {url}")
                return response.json()
                
            except requests.exceptions.RequestException as e:
                self.logger.warning(f"Request failed (attempt {attempt + 1}): {e}")
                if attempt == self.max_retries:
                    self.logger.error(f"All retry attempts failed for {url}")
                    raise APIError(f"Request failed after {self.max_retries} retries: {e}")
                
                # Exponential backoff
                time.sleep(2 ** attempt)
```

## Key Takeaways

- Follow PEP 8 for consistent, readable code
- Organize projects with clear structure and separation of concerns
- Write comprehensive tests using unittest or pytest
- Use version control effectively with meaningful commit messages
- Optimize performance with appropriate data structures and algorithms
- Implement proper logging for debugging and monitoring
- Handle errors gracefully with custom exception hierarchies
- Document code thoroughly with docstrings and comments

## What's Next?

Congratulations! You've completed the comprehensive Python learning guide. You now have the knowledge and skills to build professional-quality Python applications. Continue practicing, contributing to open source projects, and exploring specialized areas that interest you. Check out our [Resources and Next Steps](15-resources-next-steps.md) for guidance on your continued learning journey!e login timeout