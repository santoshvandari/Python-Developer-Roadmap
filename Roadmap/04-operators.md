# Operators

Operators are special symbols that perform operations on variables and values. Python supports various types of operators.

## Arithmetic Operators

Arithmetic operators perform mathematical operations.

**Basic Arithmetic:**

```python
# Basic arithmetic operations
a = 10
b = 3

print(a + b)   # Addition: 13
print(a - b)   # Subtraction: 7
print(a * b)   # Multiplication: 30
print(a / b)   # Division: 3.3333333333333335
print(a // b)  # Floor division: 3
print(a % b)   # Modulus (remainder): 1
print(a ** b)  # Exponentiation: 1000
```

**Operator Precedence:**

```python
# Order of operations (PEMDAS/BODMAS)
result = 2 + 3 * 4      # Multiplication first: 2 + 12 = 14
print(result)           # Output: 14

result = (2 + 3) * 4    # Parentheses first: 5 * 4 = 20
print(result)           # Output: 20

result = 2 ** 3 ** 2    # Exponentiation is right-associative: 2 ** (3 ** 2) = 2 ** 9 = 512
print(result)           # Output: 512

# Complex expression
result = 10 + 5 * 2 - 3 / 2 + 4 ** 2
# Step by step: 10 + 10 - 1.5 + 16 = 34.5
print(result)           # Output: 34.5
```

**Working with Different Number Types:**

```python
# Integer and float operations
int_num = 10
float_num = 3.5

print(int_num + float_num)    # Output: 13.5 (result is float)
print(int_num * float_num)    # Output: 35.0 (result is float)
print(int_num / 2)            # Output: 5.0 (division always returns float)
print(int_num // 3)           # Output: 3 (floor division with integers)
print(float_num // 2)         # Output: 1.0 (floor division with floats)
```

## Comparison Operators

Comparison operators compare values and return boolean results.

**Basic Comparisons:**

```python
x = 10
y = 5

print(x == y)   # Equal to: False
print(x != y)   # Not equal to: True
print(x > y)    # Greater than: True
print(x < y)    # Less than: False
print(x >= y)   # Greater than or equal to: True
print(x <= y)   # Less than or equal to: False
```

**Comparing Different Data Types:**

```python
# String comparisons (lexicographic order)
print("apple" < "banana")     # Output: True
print("Apple" < "apple")      # Output: True (uppercase comes first)
print("10" < "2")             # Output: True (string comparison, not numeric)

# Numeric comparisons
print(10 == 10.0)             # Output: True (values are equal)
print(10 is 10.0)             # Output: False (different types)

# List comparisons
print([1, 2, 3] == [1, 2, 3]) # Output: True
print([1, 2] < [1, 2, 3])     # Output: True (shorter list is "less")
```

**Chaining Comparisons:**

```python
# You can chain comparison operators
age = 25
print(18 <= age <= 65)        # Output: True (equivalent to: 18 <= age and age <= 65)

score = 85
print(80 <= score < 90)       # Output: True

# Multiple chaining
x = 5
print(1 < x < 10 < 20)        # Output: True
```

## Logical Operators

Logical operators combine boolean values or expressions.

**Basic Logical Operations:**

```python
# Basic logical operators
a = True
b = False

print(a and b)    # Output: False (both must be True)
print(a or b)     # Output: True (at least one must be True)
print(not a)      # Output: False (opposite of a)
print(not b)      # Output: True (opposite of b)
```

**Logical Operators with Expressions:**

```python
age = 25
has_license = True
has_car = False

# Complex logical expressions
can_drive = age >= 18 and has_license
print(f"Can drive: {can_drive}")  # Output: Can drive: True

can_drive_alone = age >= 18 and has_license and has_car
print(f"Can drive alone: {can_drive_alone}")  # Output: Can drive alone: False

needs_ride = not has_car or not has_license
print(f"Needs ride: {needs_ride}")  # Output: Needs ride: True
```

**Short-Circuit Evaluation:**

```python
# Logical operators use short-circuit evaluation
def expensive_function():
    print("This function was called!")
    return True

# In 'and' operations, if first is False, second isn't evaluated
result = False and expensive_function()  # expensive_function() is NOT called
print(result)  # Output: False

# In 'or' operations, if first is True, second isn't evaluated
result = True or expensive_function()   # expensive_function() is NOT called
print(result)  # Output: True
```

## Assignment Operators

Assignment operators assign values to variables and can combine assignment with arithmetic operations.

**Basic Assignment:**

```python
# Basic assignment
x = 10
y = x
print(f"x = {x}, y = {y}")  # Output: x = 10, y = 10
```

**Compound Assignment Operators:**

```python
# Compound assignment operators
x = 10

x += 5    # Equivalent to: x = x + 5
print(x)  # Output: 15

x -= 3    # Equivalent to: x = x - 3
print(x)  # Output: 12

x *= 2    # Equivalent to: x = x * 2
print(x)  # Output: 24

x /= 4    # Equivalent to: x = x / 4
print(x)  # Output: 6.0

x //= 2   # Equivalent to: x = x // 2
print(x)  # Output: 3.0

x %= 2    # Equivalent to: x = x % 2
print(x)  # Output: 1.0

x **= 3   # Equivalent to: x = x ** 3
print(x)  # Output: 1.0
```

**Assignment with Other Data Types:**

```python
# String compound assignment
message = "Hello"
message += " World"
print(message)  # Output: Hello World

# List compound assignment
numbers = [1, 2, 3]
numbers += [4, 5]
print(numbers)  # Output: [1, 2, 3, 4, 5]

# Multiple assignment
a, b, c = 1, 2, 3
print(f"a={a}, b={b}, c={c}")  # Output: a=1, b=2, c=3

# Swapping variables
a, b = b, a
print(f"a={a}, b={b}")  # Output: a=2, b=1
```

## Practice Exercise - Calculator

```python
def simple_calculator():
    """A simple calculator using input/output and operators."""
    
    print("=== Simple Calculator ===")
    print("Available operations: +, -, *, /, //, %, **")
    
    try:
        # Get input from user
        num1 = float(input("Enter first number: "))
        operator = input("Enter operator (+, -, *, /, //, %, **): ")
        num2 = float(input("Enter second number: "))
        
        # Perform calculation based on operator
        if operator == "+":
            result = num1 + num2
        elif operator == "-":
            result = num1 - num2
        elif operator == "*":
            result = num1 * num2
        elif operator == "/":
            if num2 != 0:
                result = num1 / num2
            else:
                print("Error: Division by zero!")
                return
        elif operator == "//":
            if num2 != 0:
                result = num1 // num2
            else:
                print("Error: Division by zero!")
                return
        elif operator == "%":
            if num2 != 0:
                result = num1 % num2
            else:
                print("Error: Division by zero!")
                return
        elif operator == "**":
            result = num1 ** num2
        else:
            print("Error: Invalid operator!")
            return
        
        # Display result
        print(f"\nResult: {num1} {operator} {num2} = {result}")
        
        # Additional information
        print(f"Result type: {type(result)}")
        if isinstance(result, float) and result.is_integer():
            print(f"As integer: {int(result)}")
            
    except ValueError:
        print("Error: Please enter valid numbers!")
    except Exception as e:
        print(f"An error occurred: {e}")

# Run the calculator
simple_calculator()
```

## Key Takeaways

- Arithmetic operators perform mathematical calculations with proper precedence
- Comparison operators return boolean values and can be chained
- Logical operators combine boolean expressions with short-circuit evaluation
- Assignment operators can combine assignment with arithmetic operations
- Use f-strings for modern, readable string formatting
- Always handle potential division by zero errors
- Understand operator precedence to write correct expressions

## What's Next?

Now that you understand operators, you're ready to learn about getting input from users and displaying output. Let's move on to [Input and Output](05-input-output.md)!