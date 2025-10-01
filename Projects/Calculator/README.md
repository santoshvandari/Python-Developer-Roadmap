# 🧮 Calculator Project

<div align="center">
  <img src="https://cdn-icons-png.flaticon.com/512/1048/1048951.png" alt="Calculator" width="200"/>
  <p><strong>Build a functional calculator from basic to advanced features</strong></p>
</div>

---

## 🎯 Project Overview

Build a calculator application that performs mathematical operations. This project will evolve from a simple command-line calculator to a feature-rich application with error handling, memory functions, and a graphical interface.

### What You'll Learn
- Variables and data types
- Arithmetic operators
- Functions and code organization
- Error handling and input validation
- User interface design
- File operations for saving calculations

### Prerequisites
Before starting this project, you should understand:
- [Basic Syntax](../../Roadmap/02-basic-syntax.md) - Variables and basic Python structure
- [Data Types](../../Roadmap/03-data-types.md) - Numbers, strings, and basic operations
- [Operators](../../Roadmap/04-operators.md) - Arithmetic and comparison operators
- [Input/Output](../../Roadmap/05-input-output.md) - Getting user input and displaying results

## 📝 Project Phases

### Phase 1: Basic Calculator (⭐)
**Time**: 1-2 hours | **Concepts**: Variables, operators, basic I/O

Create a simple calculator that performs basic arithmetic operations.

### Phase 2: Enhanced Calculator (⭐⭐)
**Time**: 2-3 hours | **Concepts**: Functions, error handling, loops

Add functions, error handling, and continuous operation.

### Phase 3: Advanced Calculator (⭐⭐⭐)
**Time**: 3-4 hours | **Concepts**: Advanced operations, memory functions

Implement scientific functions, memory storage, and history.

### Phase 4: GUI Calculator (⭐⭐⭐⭐)
**Time**: 4-6 hours | **Concepts**: GUI programming, event handling

Create a graphical user interface using tkinter.

---

## 🚀 Phase 1: Basic Calculator

### Learning Objectives
- Use arithmetic operators (+, -, *, /, **, %)
- Get user input and convert data types
- Display formatted output
- Handle division by zero

### Step-by-Step Implementation

#### Step 1: Create the basic structure

```python
# basic_calculator.py

print("Welcome to Python Calculator!")
print("Available operations: +, -, *, /, **, %")
print("-" * 40)

# Get first number
num1 = float(input("Enter first number: "))

# Get operation
operation = input("Enter operation (+, -, *, /, **, %): ")

# Get second number
num2 = float(input("Enter second number: "))

# Perform calculation
if operation == "+":
    result = num1 + num2
elif operation == "-":
    result = num1 - num2
elif operation == "*":
    result = num1 * num2
elif operation == "/":
    if num2 != 0:
        result = num1 / num2
    else:
        result = "Error: Division by zero!"
elif operation == "**":
    result = num1 ** num2
elif operation == "%":
    if num2 != 0:
        result = num1 % num2
    else:
        result = "Error: Division by zero!"
else:
    result = "Error: Invalid operation!"

# Display result
print(f"\nResult: {num1} {operation} {num2} = {result}")
print("Thank you for using Python Calculator!")
```

#### Step 2: Test your calculator

Run the program and test different operations:
```bash
python basic_calculator.py
```

**Test cases to try:**
- Addition: 10 + 5 = 15
- Division: 10 / 3 = 3.333...
- Division by zero: 10 / 0 = Error
- Power: 2 ** 3 = 8
- Modulo: 10 % 3 = 1

#### Step 3: Add input validation

```python
# basic_calculator_v2.py

def get_number(prompt):
    """Get a valid number from user input"""
    while True:
        try:
            return float(input(prompt))
        except ValueError:
            print("Please enter a valid number!")

def get_operation():
    """Get a valid operation from user input"""
    valid_operations = ["+", "-", "*", "/", "**", "%"]
    while True:
        operation = input("Enter operation (+, -, *, /, **, %): ")
        if operation in valid_operations:
            return operation
        else:
            print("Please enter a valid operation!")

print("Welcome to Python Calculator!")
print("Available operations: +, -, *, /, **, %")
print("-" * 40)

# Get inputs with validation
num1 = get_number("Enter first number: ")
operation = get_operation()
num2 = get_number("Enter second number: ")

# Perform calculation with better error handling
try:
    if operation == "+":
        result = num1 + num2
    elif operation == "-":
        result = num1 - num2
    elif operation == "*":
        result = num1 * num2
    elif operation == "/":
        result = num1 / num2
    elif operation == "**":
        result = num1 ** num2
    elif operation == "%":
        result = num1 % num2
    
    print(f"\nResult: {num1} {operation} {num2} = {result}")
except ZeroDivisionError:
    print("\nError: Cannot divide by zero!")
except OverflowError:
    print("\nError: Number too large!")
except Exception as e:
    print(f"\nError: {e}")

print("Thank you for using Python Calculator!")
```

---

## 🔧 Phase 2: Enhanced Calculator

### Learning Objectives
- Create functions for better code organization
- Implement continuous calculation loop
- Add more mathematical operations
- Handle various error scenarios

### Implementation

```python
# enhanced_calculator.py

import math

def display_menu():
    """Display calculator menu"""
    print("\n" + "=" * 50)
    print("         PYTHON CALCULATOR")
    print("=" * 50)
    print("Basic Operations:")
    print("1. Addition (+)")
    print("2. Subtraction (-)")
    print("3. Multiplication (*)")
    print("4. Division (/)")
    print("5. Power (**)")
    print("6. Modulo (%)")
    print("\nAdvanced Operations:")
    print("7. Square root (sqrt)")
    print("8. Factorial (!)")
    print("9. Logarithm (log)")
    print("10. Sine (sin)")
    print("11. Cosine (cos)")
    print("12. Tangent (tan)")
    print("\n0. Exit")
    print("=" * 50)

def get_number(prompt):
    """Get a valid number from user input"""
    while True:
        try:
            return float(input(prompt))
        except ValueError:
            print("❌ Please enter a valid number!")

def basic_operation(num1, operation, num2):
    """Perform basic arithmetic operations"""
    if operation == "+":
        return num1 + num2
    elif operation == "-":
        return num1 - num2
    elif operation == "*":
        return num1 * num2
    elif operation == "/":
        if num2 == 0:
            raise ZeroDivisionError("Cannot divide by zero")
        return num1 / num2
    elif operation == "**":
        return num1 ** num2
    elif operation == "%":
        if num2 == 0:
            raise ZeroDivisionError("Cannot divide by zero")
        return num1 % num2

def advanced_operation(operation, num):
    """Perform advanced mathematical operations"""
    if operation == "sqrt":
        if num < 0:
            raise ValueError("Cannot calculate square root of negative number")
        return math.sqrt(num)
    elif operation == "!":
        if num < 0 or num != int(num):
            raise ValueError("Factorial only works with non-negative integers")
        return math.factorial(int(num))
    elif operation == "log":
        if num <= 0:
            raise ValueError("Logarithm only works with positive numbers")
        return math.log10(num)
    elif operation == "sin":
        return math.sin(math.radians(num))
    elif operation == "cos":
        return math.cos(math.radians(num))
    elif operation == "tan":
        return math.tan(math.radians(num))

def calculator():
    """Main calculator function"""
    print("Welcome to Enhanced Python Calculator! 🧮")
    
    while True:
        display_menu()
        
        try:
            choice = input("\nChoose an operation (0-12): ")
            
            if choice == "0":
                print("\n👋 Thank you for using Python Calculator!")
                break
            
            elif choice in ["1", "2", "3", "4", "5", "6"]:
                # Basic operations
                num1 = get_number("Enter first number: ")
                num2 = get_number("Enter second number: ")
                
                operations = {
                    "1": "+", "2": "-", "3": "*", 
                    "4": "/", "5": "**", "6": "%"
                }
                
                operation = operations[choice]
                result = basic_operation(num1, operation, num2)
                print(f"\n✅ Result: {num1} {operation} {num2} = {result}")
            
            elif choice in ["7", "8", "9", "10", "11", "12"]:
                # Advanced operations
                num = get_number("Enter number: ")
                
                operations = {
                    "7": "sqrt", "8": "!", "9": "log",
                    "10": "sin", "11": "cos", "12": "tan"
                }
                
                operation = operations[choice]
                result = advanced_operation(operation, num)
                
                operation_names = {
                    "sqrt": "√", "!": "!", "log": "log₁₀",
                    "sin": "sin", "cos": "cos", "tan": "tan"
                }
                
                op_name = operation_names[operation]
                print(f"\n✅ Result: {op_name}({num}) = {result}")
            
            else:
                print("\n❌ Invalid choice! Please select 0-12.")
        
        except ZeroDivisionError as e:
            print(f"\n❌ Error: {e}")
        except ValueError as e:
            print(f"\n❌ Error: {e}")
        except Exception as e:
            print(f"\n❌ Unexpected error: {e}")
        
        # Ask if user wants to continue
        continue_calc = input("\nPress Enter to continue or 'q' to quit: ")
        if continue_calc.lower() == 'q':
            print("\n👋 Thank you for using Python Calculator!")
            break

if __name__ == "__main__":
    calculator()
```

---

## 🔥 Phase 3: Advanced Calculator

### Learning Objectives
- Implement memory functions (store, recall, clear)
- Add calculation history
- Create a persistent data storage system
- Handle complex mathematical expressions

### Implementation

```python
# advanced_calculator.py

import math
import json
import os
from datetime import datetime

class AdvancedCalculator:
    def __init__(self):
        self.memory = 0
        self.history = []
        self.history_file = "calculator_history.json"
        self.load_history()
    
    def load_history(self):
        """Load calculation history from file"""
        try:
            if os.path.exists(self.history_file):
                with open(self.history_file, 'r') as f:
                    data = json.load(f)
                    self.memory = data.get('memory', 0)
                    self.history = data.get('history', [])
        except Exception as e:
            print(f"Warning: Could not load history - {e}")
    
    def save_history(self):
        """Save calculation history to file"""
        try:
            data = {
                'memory': self.memory,
                'history': self.history
            }
            with open(self.history_file, 'w') as f:
                json.dump(data, f, indent=2)
        except Exception as e:
            print(f"Warning: Could not save history - {e}")
    
    def add_to_history(self, calculation, result):
        """Add calculation to history"""
        entry = {
            'timestamp': datetime.now().strftime('%Y-%m-%d %H:%M:%S'),
            'calculation': calculation,
            'result': result
        }
        self.history.append(entry)
        
        # Keep only last 50 calculations
        if len(self.history) > 50:
            self.history = self.history[-50:]
    
    def show_history(self):
        """Display calculation history"""
        if not self.history:
            print("\n📝 No calculation history available.")
            return
        
        print("\n📝 CALCULATION HISTORY")
        print("=" * 60)
        for i, entry in enumerate(self.history[-10:], 1):  # Show last 10
            print(f"{i:2d}. {entry['timestamp']} | {entry['calculation']} = {entry['result']}")
        
        if len(self.history) > 10:
            print(f"\n... and {len(self.history) - 10} more entries")
    
    def memory_store(self, value):
        """Store value in memory"""
        self.memory = value
        print(f"\n💾 Memory stored: {value}")
    
    def memory_recall(self):
        """Recall value from memory"""
        print(f"\n💾 Memory recall: {self.memory}")
        return self.memory
    
    def memory_clear(self):
        """Clear memory"""
        self.memory = 0
        print("\n💾 Memory cleared")
    
    def memory_add(self, value):
        """Add value to memory"""
        self.memory += value
        print(f"\n💾 Memory + {value} = {self.memory}")
    
    def evaluate_expression(self, expression):
        """Safely evaluate mathematical expression"""
        # Replace common mathematical functions
        expression = expression.replace('sqrt', 'math.sqrt')
        expression = expression.replace('sin', 'math.sin')
        expression = expression.replace('cos', 'math.cos')
        expression = expression.replace('tan', 'math.tan')
        expression = expression.replace('log', 'math.log10')
        expression = expression.replace('ln', 'math.log')
        expression = expression.replace('pi', 'math.pi')
        expression = expression.replace('e', 'math.e')
        expression = expression.replace('^', '**')
        
        # Safe evaluation with limited scope
        allowed_names = {
            "__builtins__": {},
            "math": math,
            "abs": abs,
            "round": round,
            "min": min,
            "max": max
        }
        
        try:
            result = eval(expression, allowed_names)
            return result
        except Exception as e:
            raise ValueError(f"Invalid expression: {e}")
    
    def display_menu(self):
        """Display advanced calculator menu"""
        print("\n" + "=" * 70)
        print("              ADVANCED PYTHON CALCULATOR")
        print("=" * 70)
        print("Basic Operations:")
        print("1. Calculator Mode        2. Expression Mode")
        print("\nMemory Functions:")
        print("3. Memory Store (MS)      4. Memory Recall (MR)")
        print("5. Memory Clear (MC)      6. Memory Add (M+)")
        print("\nUtilities:")
        print("7. Show History          8. Clear History")
        print("9. Constants             10. Help")
        print("\n0. Exit")
        print("=" * 70)
        print(f"Current Memory: {self.memory}")
    
    def calculator_mode(self):
        """Interactive calculator mode"""
        print("\n🧮 Calculator Mode - Enter 'back' to return to main menu")
        
        while True:
            try:
                expression = input("\nEnter calculation: ").strip()
                
                if expression.lower() in ['back', 'exit', 'quit']:
                    break
                
                if expression.lower() == 'mr':
                    result = self.memory_recall()
                    continue
                
                result = self.evaluate_expression(expression)
                print(f"\n✅ Result: {result}")
                
                # Add to history
                self.add_to_history(expression, result)
                
                # Ask about memory storage
                store = input("Store result in memory? (y/n): ").lower()
                if store == 'y':
                    self.memory_store(result)
            
            except Exception as e:
                print(f"\n❌ Error: {e}")
    
    def show_constants(self):
        """Display mathematical constants"""
        print("\n🔢 MATHEMATICAL CONSTANTS")
        print("=" * 40)
        print(f"π (pi)  = {math.pi}")
        print(f"e       = {math.e}")
        print(f"τ (tau) = {math.tau}")
        print(f"∞ (inf) = {math.inf}")
    
    def show_help(self):
        """Display help information"""
        print("\n🆘 HELP - SUPPORTED FUNCTIONS")
        print("=" * 50)
        print("Basic: +, -, *, /, **, %, (, )")
        print("Functions: sqrt(), sin(), cos(), tan()")
        print("Logarithms: log() [base 10], ln() [natural]")
        print("Constants: pi, e")
        print("Examples:")
        print("  2 + 3 * 4")
        print("  sqrt(16) + 2**3")
        print("  sin(90) * pi")
        print("  log(100) + ln(e)")
    
    def run(self):
        """Main calculator loop"""
        print("Welcome to Advanced Python Calculator! 🧮")
        
        while True:
            self.display_menu()
            
            try:
                choice = input("\nChoose an option (0-10): ").strip()
                
                if choice == "0":
                    self.save_history()
                    print("\n👋 Thank you for using Advanced Calculator!")
                    break
                
                elif choice == "1":
                    self.calculator_mode()
                
                elif choice == "2":
                    expression = input("\nEnter expression: ").strip()
                    result = self.evaluate_expression(expression)
                    print(f"\n✅ Result: {result}")
                    self.add_to_history(expression, result)
                
                elif choice == "3":
                    value = float(input("Enter value to store: "))
                    self.memory_store(value)
                
                elif choice == "4":
                    self.memory_recall()
                
                elif choice == "5":
                    self.memory_clear()
                
                elif choice == "6":
                    value = float(input("Enter value to add to memory: "))
                    self.memory_add(value)
                
                elif choice == "7":
                    self.show_history()
                
                elif choice == "8":
                    self.history.clear()
                    print("\n🗋 History cleared")
                
                elif choice == "9":
                    self.show_constants()
                
                elif choice == "10":
                    self.show_help()
                
                else:
                    print("\n❌ Invalid choice! Please select 0-10.")
            
            except Exception as e:
                print(f"\n❌ Error: {e}")
            
            input("\nPress Enter to continue...")

if __name__ == "__main__":
    calc = AdvancedCalculator()
    calc.run()
```

---

## 🎨 Phase 4: GUI Calculator (Optional)

### Learning Objectives
- Create graphical user interfaces with tkinter
- Handle button click events
- Manage application state
- Design user-friendly interfaces

### Implementation

```python
# gui_calculator.py

import tkinter as tk
from tkinter import ttk, messagebox
import math

class GUICalculator:
    def __init__(self, root):
        self.root = root
        self.root.title("Python Calculator")
        self.root.geometry("400x600")
        self.root.resizable(False, False)
        
        # Variables
        self.display_var = tk.StringVar(value="0")
        self.memory = 0
        self.current_operation = None
        self.first_operand = None
        self.should_reset_display = False
        
        self.create_widgets()
    
    def create_widgets(self):
        """Create calculator GUI widgets"""
        # Main frame
        main_frame = ttk.Frame(self.root, padding="10")
        main_frame.grid(row=0, column=0, sticky=(tk.W, tk.E, tk.N, tk.S))
        
        # Display
        display_frame = ttk.Frame(main_frame)
        display_frame.grid(row=0, column=0, columnspan=4, sticky=(tk.W, tk.E), pady=(0, 10))
        
        display = ttk.Entry(
            display_frame, 
            textvariable=self.display_var, 
            font=('Arial', 20), 
            state='readonly',
            justify='right'
        )
        display.grid(row=0, column=0, sticky=(tk.W, tk.E))
        
        # Memory indicator
        self.memory_label = ttk.Label(main_frame, text="M: 0", font=('Arial', 10))
        self.memory_label.grid(row=1, column=0, columnspan=4, sticky=tk.W)
        
        # Buttons
        self.create_buttons(main_frame)
        
        # Configure grid weights
        main_frame.columnconfigure(0, weight=1)
        main_frame.columnconfigure(1, weight=1)
        main_frame.columnconfigure(2, weight=1)
        main_frame.columnconfigure(3, weight=1)
        display_frame.columnconfigure(0, weight=1)
    
    def create_buttons(self, parent):
        """Create calculator buttons"""
        # Button configuration
        button_config = {'sticky': (tk.W, tk.E, tk.N, tk.S), 'padx': 2, 'pady': 2}
        
        # Row 2: Memory and Clear buttons
        ttk.Button(parent, text="MC", command=self.memory_clear).grid(row=2, column=0, **button_config)
        ttk.Button(parent, text="MR", command=self.memory_recall).grid(row=2, column=1, **button_config)
        ttk.Button(parent, text="MS", command=self.memory_store).grid(row=2, column=2, **button_config)
        ttk.Button(parent, text="M+", command=self.memory_add).grid(row=2, column=3, **button_config)
        
        # Row 3: Clear buttons
        ttk.Button(parent, text="C", command=self.clear).grid(row=3, column=0, **button_config)
        ttk.Button(parent, text="CE", command=self.clear_entry).grid(row=3, column=1, **button_config)
        ttk.Button(parent, text="⌫", command=self.backspace).grid(row=3, column=2, **button_config)
        ttk.Button(parent, text="±", command=self.toggle_sign).grid(row=3, column=3, **button_config)
        
        # Row 4: Functions
        ttk.Button(parent, text="√", command=lambda: self.calculate_function('sqrt')).grid(row=4, column=0, **button_config)
        ttk.Button(parent, text="x²", command=lambda: self.calculate_function('square')).grid(row=4, column=1, **button_config)
        ttk.Button(parent, text="1/x", command=lambda: self.calculate_function('reciprocal')).grid(row=4, column=2, **button_config)
        ttk.Button(parent, text="÷", command=lambda: self.set_operation('/')).grid(row=4, column=3, **button_config)
        
        # Rows 5-8: Number pad and operations
        buttons = [
            ['7', '8', '9', '×'],
            ['4', '5', '6', '-'],
            ['1', '2', '3', '+'],
            ['0', '.', '=', '=']
        ]
        
        for i, row in enumerate(buttons, start=5):
            for j, text in enumerate(row):
                if text.isdigit() or text == '.':
                    cmd = lambda t=text: self.input_number(t)
                elif text == '×':
                    cmd = lambda: self.set_operation('*')
                elif text in ['+', '-']:
                    cmd = lambda t=text: self.set_operation(t)
                elif text == '=':
                    cmd = self.calculate
                    if j == 3:  # Make = button span 2 columns
                        continue
                
                btn = ttk.Button(parent, text=text, command=cmd)
                
                if text == '=' and j == 2:
                    btn.grid(row=i, column=j, columnspan=2, **button_config)
                elif text == '0':
                    btn.grid(row=i, column=j, columnspan=2, **button_config)
                    j += 1  # Skip next column
                else:
                    btn.grid(row=i, column=j, **button_config)
    
    def input_number(self, digit):
        """Handle number input"""
        current = self.display_var.get()
        
        if self.should_reset_display or current == "0":
            if digit == '.':
                self.display_var.set("0.")
            else:
                self.display_var.set(digit)
            self.should_reset_display = False
        else:
            if digit == '.' and '.' in current:
                return  # Don't add multiple decimal points
            self.display_var.set(current + digit)
    
    def set_operation(self, operation):
        """Set the operation for calculation"""
        try:
            self.first_operand = float(self.display_var.get())
            self.current_operation = operation
            self.should_reset_display = True
        except ValueError:
            messagebox.showerror("Error", "Invalid number")
    
    def calculate(self):
        """Perform calculation"""
        if self.current_operation is None or self.first_operand is None:
            return
        
        try:
            second_operand = float(self.display_var.get())
            
            if self.current_operation == '+':
                result = self.first_operand + second_operand
            elif self.current_operation == '-':
                result = self.first_operand - second_operand
            elif self.current_operation == '*':
                result = self.first_operand * second_operand
            elif self.current_operation == '/':
                if second_operand == 0:
                    raise ZeroDivisionError("Cannot divide by zero")
                result = self.first_operand / second_operand
            
            self.display_var.set(str(result))
            self.current_operation = None
            self.first_operand = None
            self.should_reset_display = True
            
        except (ValueError, ZeroDivisionError) as e:
            messagebox.showerror("Error", str(e))
            self.clear()
    
    def calculate_function(self, function):
        """Calculate mathematical functions"""
        try:
            value = float(self.display_var.get())
            
            if function == 'sqrt':
                if value < 0:
                    raise ValueError("Cannot calculate square root of negative number")
                result = math.sqrt(value)
            elif function == 'square':
                result = value ** 2
            elif function == 'reciprocal':
                if value == 0:
                    raise ZeroDivisionError("Cannot divide by zero")
                result = 1 / value
            
            self.display_var.set(str(result))
            self.should_reset_display = True
            
        except (ValueError, ZeroDivisionError) as e:
            messagebox.showerror("Error", str(e))
    
    def clear(self):
        """Clear everything"""
        self.display_var.set("0")
        self.current_operation = None
        self.first_operand = None
        self.should_reset_display = False
    
    def clear_entry(self):
        """Clear current entry"""
        self.display_var.set("0")
    
    def backspace(self):
        """Remove last character"""
        current = self.display_var.get()
        if len(current) > 1:
            self.display_var.set(current[:-1])
        else:
            self.display_var.set("0")
    
    def toggle_sign(self):
        """Toggle positive/negative sign"""
        try:
            value = float(self.display_var.get())
            self.display_var.set(str(-value))
        except ValueError:
            pass
    
    def memory_store(self):
        """Store current value in memory"""
        try:
            self.memory = float(self.display_var.get())
            self.memory_label.config(text=f"M: {self.memory}")
        except ValueError:
            messagebox.showerror("Error", "Invalid number")
    
    def memory_recall(self):
        """Recall value from memory"""
        self.display_var.set(str(self.memory))
        self.should_reset_display = True
    
    def memory_clear(self):
        """Clear memory"""
        self.memory = 0
        self.memory_label.config(text="M: 0")
    
    def memory_add(self):
        """Add current value to memory"""
        try:
            value = float(self.display_var.get())
            self.memory += value
            self.memory_label.config(text=f"M: {self.memory}")
        except ValueError:
            messagebox.showerror("Error", "Invalid number")

if __name__ == "__main__":
    root = tk.Tk()
    app = GUICalculator(root)
    root.mainloop()
```

---

## 📚 Testing Your Calculator

### Test Cases

#### Basic Operations
```python
# Test file: test_calculator.py

def test_basic_operations():
    """Test basic arithmetic operations"""
    test_cases = [
        (5, '+', 3, 8),
        (10, '-', 4, 6),
        (6, '*', 7, 42),
        (15, '/', 3, 5),
        (2, '**', 3, 8),
        (17, '%', 5, 2)
    ]
    
    for num1, op, num2, expected in test_cases:
        # Test your calculator functions here
        print(f"Testing: {num1} {op} {num2} = {expected}")

def test_edge_cases():
    """Test edge cases and error conditions"""
    edge_cases = [
        (10, '/', 0, "Error"),  # Division by zero
        (9, '/', 3, 3),        # Normal division
        (-5, '+', 3, -2),      # Negative numbers
        (0.1, '+', 0.2, 0.3),  # Floating point
    ]
    
    for num1, op, num2, expected in edge_cases:
        print(f"Testing edge case: {num1} {op} {num2}")

if __name__ == "__main__":
    test_basic_operations()
    test_edge_cases()
```

---

## 🚀 Project Extensions

### Beginner Extensions
1. **Unit Converter**: Add length, weight, temperature conversions
2. **Percentage Calculator**: Calculate tips, discounts, percentages
3. **Basic Statistics**: Mean, median, mode of number lists

### Intermediate Extensions
1. **Graphing Calculator**: Plot mathematical functions
2. **Currency Converter**: Real-time exchange rates
3. **Programmer Calculator**: Binary, hexadecimal, octal operations
4. **Loan Calculator**: Mortgage and loan payment calculations

### Advanced Extensions
1. **Symbolic Math**: Using SymPy for algebraic expressions
2. **Voice Calculator**: Speech recognition input
3. **Web Calculator**: Flask/Django web application
4. **Mobile App**: Using Kivy for cross-platform mobile apps

---

## 🛠️ Troubleshooting

### Common Issues

**Problem**: "Invalid literal for int() with base 10"
**Solution**: Use `try-except` blocks and validate input

**Problem**: Division by zero errors
**Solution**: Check for zero before division operations

**Problem**: Floating point precision issues
**Solution**: Use `round()` function or `decimal` module for precise calculations

**Problem**: GUI buttons not responding
**Solution**: Check that command functions are properly defined and connected

### Debugging Tips

1. **Print Debugging**: Add print statements to see variable values
2. **Step Through Code**: Use a debugger or trace through logic manually
3. **Test Small Parts**: Test individual functions before combining
4. **Check Data Types**: Ensure variables are the expected type

---

## 🎆 Conclusion

Congratulations! You've built a comprehensive calculator application that demonstrates:

- **Programming Fundamentals**: Variables, functions, loops, conditionals
- **Error Handling**: Graceful handling of invalid input and edge cases
- **Code Organization**: Breaking complex programs into manageable functions
- **User Interface Design**: Both command-line and graphical interfaces
- **Data Persistence**: Saving and loading calculation history
- **Testing**: Writing and running test cases

### Next Steps

1. **Add More Features**: Implement the extensions suggested above
2. **Share Your Work**: Upload to GitHub and create a portfolio
3. **Learn More**: Move on to the next project in your learning path
4. **Help Others**: Share your experience and help other learners

### Skills Practiced

✅ **Variables and Data Types**
✅ **Arithmetic Operations**
✅ **Functions and Code Organization**
✅ **Error Handling**
✅ **User Input Validation**
✅ **File Operations**
✅ **Object-Oriented Programming**
✅ **GUI Programming**
✅ **Testing and Debugging**

**Great job on completing the Calculator project!** 🎉

Ready for your next challenge? Check out the [Number Guessing Game](../NumberGuessingGame/README.md) or explore other projects in the [Projects Directory](../README.md).