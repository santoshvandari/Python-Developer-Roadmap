# File Handling

File handling is essential for reading data, storing results, and working with external resources. Python provides comprehensive tools for working with various file formats.

## Reading and Writing Files

### Basic File Operations

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

### Different File Modes

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
```

### Error Handling with Files

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

## Working with CSV Files

### Basic CSV Operations

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
```### 
Advanced CSV Operations

```python
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

## JSON File Operations

### Working with JSON Data

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
```# Readi
ng JSON files
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

## File Paths with Pathlib

### Modern Path Handling

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

# Run pathlib demonstrations
pathlib_basics()
project_dir = pathlib_file_operations()
```

## Binary Files and Serialization

### Working with Binary Data

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
pickle_operations()
```

## Key Takeaways

- Always use context managers (`with` statement) for file operations
- Handle file-related exceptions appropriately
- Use pathlib for modern, cross-platform path handling
- CSV and JSON modules provide robust data file handling
- Binary files require special handling with struct and pickle
- File system operations should be performed carefully with proper error handling

## What's Next?

Now that you understand file handling, you're ready to explore popular Python libraries that will expand your capabilities. Let's move on to [Popular Libraries](13-popular-libraries.md)!