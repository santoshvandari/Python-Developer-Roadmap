# Input and Output

Interacting with users through input and output is fundamental to most programs.

## Getting User Input

The `input()` function allows you to get text input from users.

**Basic Input:**

```python
# Getting user input
name = input("What's your name? ")
print(f"Hello, {name}!")

# Input always returns a string
age_str = input("How old are you? ")
print(f"You entered: {age_str} (type: {type(age_str)})")
```

**Converting Input Types:**

```python
# Converting string input to numbers
age = int(input("Enter your age: "))
height = float(input("Enter your height in feet: "))

print(f"Age: {age} (type: {type(age)})")
print(f"Height: {height} (type: {type(height)})")

# Calculating with converted input
birth_year = 2024 - age
print(f"You were born around {birth_year}")
```

**Handling Input Errors:**

```python
# Basic error handling for input
try:
    number = int(input("Enter a number: "))
    print(f"You entered: {number}")
except ValueError:
    print("That's not a valid number!")

# More robust input handling
def get_integer(prompt):
    while True:
        try:
            return int(input(prompt))
        except ValueError:
            print("Please enter a valid integer.")

age = get_integer("Enter your age: ")
print(f"Your age is {age}")
```

**Multiple Inputs:**

```python
# Getting multiple values in one line
data = input("Enter your name, age, and city (separated by commas): ")
name, age, city = data.split(", ")
print(f"Name: {name}, Age: {age}, City: {city}")

# Getting multiple numbers
numbers_str = input("Enter numbers separated by spaces: ")
numbers = [int(x) for x in numbers_str.split()]
print(f"Numbers: {numbers}")
print(f"Sum: {sum(numbers)}")
```

## Printing Output

The `print()` function is used to display output to the user.

**Basic Printing:**

```python
# Basic print statements
print("Hello, World!")
print("Python", "is", "awesome")  # Multiple arguments
print("Line 1")
print("Line 2")
```

**Print Function Parameters:**

```python
# sep parameter (separator between arguments)
print("apple", "banana", "cherry", sep=", ")  # Output: apple, banana, cherry
print("2024", "12", "25", sep="-")            # Output: 2024-12-25

# end parameter (what to print at the end)
print("Hello", end=" ")
print("World")  # Output: Hello World (on same line)

print("Loading", end="")
for i in range(3):
    print(".", end="")
print(" Done!")  # Output: Loading... Done!
```

**Formatting Output:**

```python
name = "Alice"
age = 30
salary = 75000.50

# f-strings (recommended for Python 3.6+)
print(f"Name: {name}")
print(f"Age: {age}")
print(f"Salary: ${salary:,.2f}")  # Output: Salary: $75,000.50

# .format() method
print("Name: {}, Age: {}".format(name, age))
print("Salary: ${:,.2f}".format(salary))

# % formatting (older style)
print("Name: %s, Age: %d" % (name, age))
```

**Advanced Formatting:**

```python
# Number formatting
pi = 3.14159265359
print(f"Pi: {pi:.2f}")        # Output: Pi: 3.14
print(f"Pi: {pi:.4f}")        # Output: Pi: 3.1416

# Percentage formatting
score = 0.875
print(f"Score: {score:.1%}")  # Output: Score: 87.5%

# Padding and alignment
print(f"{'Name':<10} {'Age':>5} {'City':^15}")
print(f"{'Alice':<10} {25:>5} {'New York':^15}")
print(f"{'Bob':<10} {30:>5} {'Chicago':^15}")

# Output:
# Name            Age      City
# Alice            25    New York
# Bob              30     Chicago
```

**Printing Data Structures:**

```python
# Printing lists, dictionaries, etc.
numbers = [1, 2, 3, 4, 5]
person = {"name": "Alice", "age": 30, "city": "New York"}

print("Numbers:", numbers)
print("Person:", person)

# Pretty printing for better readability
import pprint
complex_data = {
    "users": [
        {"name": "Alice", "age": 30, "hobbies": ["reading", "swimming"]},
        {"name": "Bob", "age": 25, "hobbies": ["gaming", "cooking"]}
    ]
}

print("Regular print:")
print(complex_data)

print("\nPretty print:")
pprint.pprint(complex_data)
```

## Practice Exercise - Interactive Program

```python
def user_profile_creator():
    """Create a user profile with input validation."""
    
    print("=== User Profile Creator ===")
    print("Let's create your profile!\n")
    
    # Get basic information
    name = input("Enter your full name: ").strip()
    while not name:
        print("Name cannot be empty!")
        name = input("Enter your full name: ").strip()
    
    # Get age with validation
    while True:
        try:
            age = int(input("Enter your age: "))
            if age < 0 or age > 150:
                print("Please enter a realistic age (0-150)")
                continue
            break
        except ValueError:
            print("Please enter a valid number for age")
    
    # Get email
    email = input("Enter your email: ").strip()
    while "@" not in email or "." not in email:
        print("Please enter a valid email address")
        email = input("Enter your email: ").strip()
    
    # Get hobbies
    hobbies_input = input("Enter your hobbies (separated by commas): ")
    hobbies = [hobby.strip() for hobby in hobbies_input.split(",") if hobby.strip()]
    
    # Get favorite number
    while True:
        try:
            fav_number = float(input("Enter your favorite number: "))
            break
        except ValueError:
            print("Please enter a valid number")
    
    # Display profile
    print("\n" + "="*50)
    print("YOUR PROFILE")
    print("="*50)
    print(f"Name: {name}")
    print(f"Age: {age} years old")
    print(f"Email: {email}")
    print(f"Favorite Number: {fav_number}")
    
    if hobbies:
        print("Hobbies:")
        for i, hobby in enumerate(hobbies, 1):
            print(f"  {i}. {hobby}")
    else:
        print("Hobbies: None specified")
    
    # Calculate some fun facts
    days_lived = age * 365
    print(f"\nFun Facts:")
    print(f"- You've lived approximately {days_lived:,} days!")
    print(f"- Your name has {len(name)} characters")
    print(f"- You have {len(hobbies)} hobbies listed")
    
    # Ask if they want to save
    save = input("\nWould you like to save this profile? (yes/no): ").lower()
    if save in ['yes', 'y']:
        filename = f"{name.replace(' ', '_').lower()}_profile.txt"
        try:
            with open(filename, 'w') as file:
                file.write(f"User Profile\n")
                file.write(f"============\n")
                file.write(f"Name: {name}\n")
                file.write(f"Age: {age}\n")
                file.write(f"Email: {email}\n")
                file.write(f"Favorite Number: {fav_number}\n")
                file.write(f"Hobbies: {', '.join(hobbies)}\n")
            print(f"Profile saved to {filename}")
        except Exception as e:
            print(f"Error saving file: {e}")
    
    print("\nThank you for creating your profile!")

# Run the profile creator
user_profile_creator()
```

## Key Takeaways

- `input()` always returns strings that need conversion for numeric operations
- `print()` has many formatting options for professional output
- Always handle potential input errors in real applications
- Use f-strings for modern, readable string formatting
- Validate user input to ensure data quality
- Consider user experience when designing input/output interactions

## What's Next?

Now that you can interact with users through input and output, you're ready to learn about making decisions in your programs. Let's move on to [Control Structures](06-control-structures.md)!