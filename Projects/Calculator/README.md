# Calculator Project

Build a calculator application that performs mathematical operations, starting from basic arithmetic and progressing to advanced features.

## Project Overview

**What you'll build**: A calculator that can perform basic arithmetic operations, handle user input validation, and optionally include a graphical interface.

**What you'll learn**:
- Working with numbers and arithmetic operators
- Handling user input and validation
- Error handling for edge cases
- Organizing code with functions
- Creating simple user interfaces

## Project Phases

### Phase 1: Basic Calculator
**Features**: Basic arithmetic operations (+, -, *, /, **, %)
**Time**: 1-2 hours

Create a simple calculator that:
- Asks user for two numbers and an operation
- Performs the calculation
- Displays the result
- Handles division by zero

**Key concepts**: Variables, operators, input/output, basic conditionals

### Phase 2: Enhanced Calculator  
**Features**: Input validation, continuous operation, error handling
**Time**: 2-3 hours

Improve your calculator to:
- Validate user input (numbers and operations)
- Allow multiple calculations in one session
- Handle various error conditions gracefully
- Provide clear user instructions

**Key concepts**: Functions, loops, exception handling, input validation

### Phase 3: Advanced Calculator
**Features**: Scientific functions, memory operations, calculation history
**Time**: 3-4 hours

Add advanced features:
- Scientific functions (sqrt, sin, cos, log, etc.)
- Memory functions (store, recall, clear)
- Save calculation history to file
- Expression evaluation

**Key concepts**: Math module, file operations, data persistence, classes

### Phase 4: GUI Calculator (Optional)
**Features**: Graphical user interface with buttons
**Time**: 4-6 hours

Create a visual calculator:
- Button-based interface
- Display screen for numbers and results
- Mouse and keyboard input support
- Professional calculator appearance

**Key concepts**: GUI programming (tkinter), event handling, interface design

## Implementation Guide

### Getting Started

1. **Set up your environment**
   ```bash
   mkdir calculator_project
   cd calculator_project
   ```

2. **Start with basic structure**
   ```python
   # basic_calculator.py
   print("Welcome to Python Calculator!")
   
   # Get user input
   num1 = float(input("Enter first number: "))
   operation = input("Enter operation (+, -, *, /): ")
   num2 = float(input("Enter second number: "))
   
   # Perform calculation and display result
   ```

3. **Add error handling**
   - Handle invalid number input
   - Check for division by zero
   - Validate operation choices

4. **Organize with functions**
   - Create separate functions for each operation
   - Add input validation functions
   - Implement main program loop

### Testing Your Calculator

**Test cases to verify**:
- Basic operations: 5 + 3, 10 - 4, 6 * 7, 15 / 3
- Edge cases: Division by zero, invalid input
- Scientific functions: sqrt(16), sin(90), log(100)
- Memory operations: Store, recall, clear

### Common Issues and Solutions

**Problem**: "ValueError: invalid literal for float()"
**Solution**: Add try-except blocks around input conversion

**Problem**: Division by zero error
**Solution**: Check if denominator is zero before division

**Problem**: Invalid operation entered
**Solution**: Validate operation against allowed list

## Extensions and Improvements

### Beginner Extensions
- Unit converter (length, weight, temperature)
- Percentage calculator (tips, discounts)
- Basic statistics (average, min, max)

### Intermediate Extensions
- Graphing calculator with plot display
- Currency converter with live rates
- Programmer calculator (binary, hex operations)

### Advanced Extensions
- Voice-controlled calculator
- Web-based calculator interface
- Multi-line expression parser
- Plugin system for custom functions

## File Structure

```
calculator_project/
├── basic_calculator.py      # Phase 1 implementation
├── enhanced_calculator.py   # Phase 2 with functions
├── advanced_calculator.py   # Phase 3 with classes
├── gui_calculator.py        # Phase 4 GUI version
├── calculator_history.json  # Saved calculations
└── README.md               # Project documentation
```

## Learning Outcomes

After completing this project, you'll understand:
- How to handle user input and validate data
- Basic error handling and exception management
- Function organization and code structure
- File operations for data persistence
- GUI programming fundamentals
- Mathematical operations in Python

## Next Steps

Once you've completed your calculator:
1. Add your own creative features
2. Share your code on GitHub
3. Try the Number Guessing Game project
4. Explore other projects in the collection

Congratulations on building your first Python project!