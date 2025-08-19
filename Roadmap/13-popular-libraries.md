# Popular Libraries

Python's strength lies in its extensive ecosystem of libraries. Here are the most important libraries that every Python developer should know.

## NumPy for Numerical Computing

NumPy is the foundation of scientific computing in Python, providing powerful array operations and mathematical functions.

### Array Creation and Basic Operations

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

### Array Manipulation and Mathematical Operations

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

## Pandas for Data Manipulation

Pandas provides powerful data structures and analysis tools for working with structured data.

### DataFrames and Series

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
```### D
ata Analysis and Manipulation

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

## Requests for HTTP Operations

The requests library simplifies HTTP operations for web APIs and web scraping.

### Basic HTTP Requests

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

## Matplotlib for Data Visualization

Matplotlib is the primary plotting library for creating static, animated, and interactive visualizations.

### Basic Plotting

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
```## Web
 Frameworks

### Flask - Lightweight Web Framework

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

## Database Connectivity

### SQLite Database Operations

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

## Other Essential Libraries

### Beautiful Soup for Web Scraping

```python
# Note: This is a conceptual example
# You would need to install: pip install beautifulsoup4 requests

"""
from bs4 import BeautifulSoup
import requests

def scrape_website():
    # Scrape a website (example)
    url = "https://example.com"
    response = requests.get(url)
    
    if response.status_code == 200:
        soup = BeautifulSoup(response.content, 'html.parser')
        
        # Find all links
        links = soup.find_all('a')
        for link in links:
            print(link.get('href'))
        
        # Find specific elements
        title = soup.find('title').text
        print(f"Page title: {title}")
"""
```

### DateTime for Date and Time Operations

```python
from datetime import datetime, date, timedelta
import calendar

# Current date and time
now = datetime.now()
today = date.today()

print(f"Current datetime: {now}")
print(f"Today's date: {today}")
print(f"Current year: {now.year}")
print(f"Current month: {now.month}")
print(f"Current day: {now.day}")

# Date arithmetic
tomorrow = today + timedelta(days=1)
last_week = today - timedelta(weeks=1)
next_month = today + timedelta(days=30)

print(f"Tomorrow: {tomorrow}")
print(f"Last week: {last_week}")
print(f"Next month (approx): {next_month}")

# Formatting dates
formatted_date = now.strftime("%Y-%m-%d %H:%M:%S")
print(f"Formatted: {formatted_date}")

# Parsing dates
date_string = "2024-12-25"
parsed_date = datetime.strptime(date_string, "%Y-%m-%d")
print(f"Parsed date: {parsed_date}")

# Working with timezones (requires pytz)
"""
import pytz

utc_now = datetime.now(pytz.UTC)
eastern = pytz.timezone('US/Eastern')
eastern_time = utc_now.astimezone(eastern)
print(f"Eastern time: {eastern_time}")
"""
```

### Collections for Specialized Data Structures

```python
from collections import Counter, defaultdict, deque, namedtuple

# Counter for counting
text = "hello world"
letter_count = Counter(text)
print(f"Letter frequencies: {letter_count}")
print(f"Most common: {letter_count.most_common(3)}")

# defaultdict for default values
dd = defaultdict(list)
dd['fruits'].append('apple')
dd['fruits'].append('banana')
dd['vegetables'].append('carrot')
print(f"Default dict: {dict(dd)}")

# deque for efficient append/pop operations
dq = deque([1, 2, 3])
dq.appendleft(0)  # Add to left
dq.append(4)      # Add to right
print(f"Deque: {dq}")
print(f"Pop left: {dq.popleft()}")
print(f"Pop right: {dq.pop()}")

# namedtuple for structured data
Person = namedtuple('Person', ['name', 'age', 'city'])
person = Person('Alice', 30, 'New York')
print(f"Person: {person}")
print(f"Name: {person.name}, Age: {person.age}")
```

## Key Takeaways

- NumPy provides efficient array operations and mathematical functions
- Pandas excels at data manipulation and analysis with DataFrames
- Requests simplifies HTTP operations and API interactions
- Matplotlib creates comprehensive data visualizations
- Flask enables rapid web application development
- SQLite provides lightweight database functionality
- These libraries form the foundation of most Python data science and web development projects

## What's Next?

Now that you're familiar with popular libraries, you're ready to learn about professional development practices and best practices. Let's move on to [Best Practices](14-best-practices.md)!