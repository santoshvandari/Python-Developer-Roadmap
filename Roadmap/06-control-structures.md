# Control Structures

Control structures allow you to control the flow of your program's execution. They enable you to make decisions, repeat actions, and create more complex program logic.

## Conditional Statements

Conditional statements allow your program to make decisions based on different conditions.

### Basic If Statements

```python
# Simple if statement
age = 18
if age >= 18:
    print("You are an adult")

# If-else statement
temperature = 25
if temperature > 30:
    print("It's hot outside")
else:
    print("It's not too hot")

# Multiple conditions with elif
score = 85
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
elif score >= 60:
    grade = "D"
else:
    grade = "F"

print(f"Your grade is: {grade}")
```

### Complex Conditions

```python
# Using logical operators in conditions
age = 25
has_license = True
has_car = True

if age >= 18 and has_license:
    if has_car:
        print("You can drive your own car")
    else:
        print("You can drive but need to borrow a car")
else:
    print("You cannot drive")

# Combining multiple conditions
weather = "sunny"
temperature = 22
if weather == "sunny" and temperature > 20:
    print("Perfect day for a picnic!")
elif weather == "rainy" or temperature < 10:
    print("Better stay inside")
else:
    print("Decent weather for outdoor activities")
```

### Ternary Operator

```python
# Ternary operator for simple conditions
age = 20
status = "adult" if age >= 18 else "minor"
print(f"Status: {status}")

# Multiple ternary operators (use sparingly)
score = 85
grade = "A" if score >= 90 else "B" if score >= 80 else "C" if score >= 70 else "F"
print(f"Grade: {grade}")
```

## For Loops

For loops are used to iterate over sequences or other iterable objects.

### Basic For Loops

```python
# Iterating over a list
fruits = ["apple", "banana", "cherry", "date"]
for fruit in fruits:
    print(f"I like {fruit}")

# Iterating over a string
word = "Python"
for letter in word:
    print(letter)

# Using range() for numeric loops
for i in range(5):
    print(f"Count: {i}")  # Output: 0, 1, 2, 3, 4

# Range with start, stop, and step
for i in range(2, 10, 2):
    print(f"Even number: {i}")  # Output: 2, 4, 6, 8
```

### Advanced For Loop Techniques

```python
# Using enumerate() to get index and value
colors = ["red", "green", "blue"]
for index, color in enumerate(colors):
    print(f"Color {index}: {color}")

# Starting enumerate from a different number
for index, color in enumerate(colors, start=1):
    print(f"Color {index}: {color}")

# Iterating over dictionary
person = {"name": "Alice", "age": 30, "city": "New York"}
for key, value in person.items():
    print(f"{key}: {value}")

# Iterating over multiple lists with zip()
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
cities = ["New York", "London", "Tokyo"]

for name, age, city in zip(names, ages, cities):
    print(f"{name} is {age} years old and lives in {city}")
```

## While Loops

While loops continue executing as long as a condition remains true.

### Basic While Loops

```python
# Simple while loop
count = 0
while count < 5:
    print(f"Count: {count}")
    count += 1

# While loop with user input
password = ""
while password != "secret":
    password = input("Enter password: ")
    if password != "secret":
        print("Incorrect password, try again")
print("Access granted!")
```

### While Loops with Complex Conditions

```python
# Multiple conditions in while loop
attempts = 0
max_attempts = 3
success = False

while attempts < max_attempts and not success:
    user_input = input("Enter 'yes' to continue: ")
    if user_input.lower() == "yes":
        success = True
        print("Success!")
    else:
        attempts += 1
        print(f"Attempt {attempts} failed")

if not success:
    print("Maximum attempts reached")
```

## Break and Continue

`break` and `continue` statements provide additional control over loop execution.

### Using Break

```python
# Break exits the loop immediately
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for num in numbers:
    if num == 6:
        print("Found 6, stopping loop")
        break
    print(num)
# Output: 1, 2, 3, 4, 5, Found 6, stopping loop

# Break in while loop
count = 0
while True:
    count += 1
    if count > 5:
        break
    print(count)
print("Loop ended")
```

### Using Continue

```python
# Continue skips the rest of the current iteration
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for num in numbers:
    if num % 2 == 0:  # Skip even numbers
        continue
    print(f"Odd number: {num}")
# Output: Odd number: 1, Odd number: 3, Odd number: 5, etc.

# Continue in while loop
count = 0
while count < 10:
    count += 1
    if count % 3 == 0:  # Skip multiples of 3
        continue
    print(count)
```

## List Comprehensions

List comprehensions provide a concise way to create lists.

### Basic List Comprehensions

```python
# Traditional loop to create a list
squares = []
for i in range(10):
    squares.append(i ** 2)
print(squares)

# List comprehension (more Pythonic)
squares = [i ** 2 for i in range(10)]
print(squares)

# List comprehension with condition
even_squares = [i ** 2 for i in range(10) if i % 2 == 0]
print(even_squares)  # Output: [0, 4, 16, 36, 64]
```

### Advanced Comprehensions

```python
# More complex list comprehensions
words = ["hello", "world", "python", "programming"]
lengths = [len(word) for word in words]
print(lengths)  # Output: [5, 5, 6, 11]

# Nested list comprehension
matrix = [[i * j for j in range(1, 4)] for i in range(1, 4)]
print(matrix)  # Output: [[1, 2, 3], [2, 4, 6], [3, 6, 9]]

# Dictionary comprehension
square_dict = {x: x**2 for x in range(5)}
print(square_dict)  # Output: {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}

# Set comprehension
unique_lengths = {len(word) for word in words}
print(unique_lengths)  # Output: {5, 6, 11}
```

## Practice Exercise - Number Guessing Game

```python
import random

def number_guessing_game():
    """A complete number guessing game using control structures."""
    
    print("=== Number Guessing Game ===")
    print("I'm thinking of a number between 1 and 100")
    
    # Game settings
    secret_number = random.randint(1, 100)
    max_attempts = 7
    attempts = 0
    
    while attempts < max_attempts:
        try:
            # Get user input
            guess = int(input(f"Attempt {attempts + 1}/{max_attempts} - Enter your guess: "))
            attempts += 1
            
            # Check the guess
            if guess == secret_number:
                print(f"Congratulations! You guessed it in {attempts} attempts!")
                break
            elif guess < secret_number:
                print("Too low!")
            else:
                print("Too high!")
            
            # Give hints based on how close they are
            difference = abs(guess - secret_number)
            if difference <= 5:
                print("You're very close!")
            elif difference <= 15:
                print("You're getting warmer!")
            
        except ValueError:
            print("Please enter a valid number!")
            attempts -= 1  # Don't count invalid input as an attempt
            continue
    
    else:
        # This runs if the while loop completes without breaking
        print(f"Game over! The number was {secret_number}")
    
    # Ask if they want to play again
    play_again = input("Do you want to play again? (yes/no): ")
    if play_again.lower() in ['yes', 'y']:
        number_guessing_game()  # Recursive call to play again

# Run the game
number_guessing_game()
```

## Key Takeaways

- Use `if/elif/else` for decision making based on conditions
- `for` loops are ideal when you know the number of iterations
- `while` loops are perfect when the condition determines when to stop
- `break` exits a loop immediately, `continue` skips to the next iteration
- List comprehensions provide a concise way to create lists
- Always consider edge cases and input validation in real applications

## What's Next?

Now that you understand control structures, you're ready to learn about organizing your code into reusable functions. Let's move on to [Functions](07-functions.md)!