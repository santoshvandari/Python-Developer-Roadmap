# Getting Started

## Why Python?

Python is one of the most popular and versatile programming languages in the world. Here's why it's perfect for beginners and professionals alike:

**Easy to Learn**
- Simple, readable syntax that resembles natural language
- Minimal setup required to start coding
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

## Installation

### Windows
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

### macOS
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

### Linux (Ubuntu/Debian)
```bash
# Update package list
sudo apt update

# Install Python 3 and pip
sudo apt install python3 python3-pip

# Verify installation
python3 --version
pip3 --version
```

### Linux (CentOS/RHEL/Fedora)
```bash
# For CentOS/RHEL
sudo yum install python3 python3-pip

# For Fedora
sudo dnf install python3 python3-pip

# Verify installation
python3 --version
pip3 --version
```

## Your First Python Program

Let's write your first Python program! This traditional "Hello, World!" program will verify that Python is working correctly.

### Method 1: Interactive Python Shell
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

### Method 2: Python Script File
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

🎉 **Congratulations!** You've just written and executed your first Python program!

## Development Environment Setup

While you can write Python code in any text editor, using a proper development environment will make your coding experience much better.

### Recommended IDEs and Editors

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

### Setting Up Visual Studio Code for Python

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

### Essential Terminal/Command Prompt Commands

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

### Troubleshooting Common Issues

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

## What's Next?

Now that you have Python installed and your development environment set up, you're ready to dive into programming! Here's what we'll cover next:

1. **Basic Syntax** - Variables, comments, and code structure
2. **Data Types** - Numbers, strings, lists, and more
3. **Operators** - Mathematical and logical operations
4. **Input/Output** - Getting user input and displaying results

Ready to start coding? Let's move on to [Basic Syntax](02-basic-syntax.md)!