# Object-Oriented Programming

Object-Oriented Programming (OOP) is a programming paradigm that organizes code into classes and objects, making it easier to model real-world entities and relationships.

## Classes and Objects

### Basic Class Definition

```python
class Person:
    """A class representing a person."""
    
    # Class variable (shared by all instances)
    species = "Homo sapiens"
    
    def __init__(self, name, age):
        """Initialize a new Person instance."""
        # Instance variables (unique to each instance)
        self.name = name
        self.age = age
        self.friends = []
    
    def introduce(self):
        """Return an introduction string."""
        return f"Hi, I'm {self.name} and I'm {self.age} years old"
    
    def have_birthday(self):
        """Increase age by 1."""
        self.age += 1
        return f"Happy birthday! {self.name} is now {self.age}"
    
    def add_friend(self, friend):
        """Add a friend to the friends list."""
        if friend not in self.friends:
            self.friends.append(friend)
            return f"{friend} is now {self.name}'s friend"
        return f"{friend} is already {self.name}'s friend"

# Creating objects (instances)
person1 = Person("Alice", 30)
person2 = Person("Bob", 25)

# Using object methods
print(person1.introduce())  # Output: Hi, I'm Alice and I'm 30 years old
print(person1.have_birthday())  # Output: Happy birthday! Alice is now 31

# Accessing attributes
print(f"Name: {person1.name}")  # Output: Name: Alice
print(f"Species: {person1.species}")  # Output: Species: Homo sapiens
```

### Class vs Instance Variables

```python
class BankAccount:
    """A class representing a bank account."""
    
    # Class variables
    bank_name = "Python Bank"
    interest_rate = 0.02
    total_accounts = 0
    
    def __init__(self, account_holder, initial_balance=0):
        """Initialize a new bank account."""
        # Instance variables
        self.account_holder = account_holder
        self.balance = initial_balance
        self.transaction_history = []
        
        # Increment class variable
        BankAccount.total_accounts += 1
        self.account_number = f"ACC{BankAccount.total_accounts:04d}"
    
    def deposit(self, amount):
        """Deposit money to the account."""
        if amount > 0:
            self.balance += amount
            self.transaction_history.append(f"Deposited ${amount}")
            return f"Deposited ${amount}. New balance: ${self.balance}"
        return "Invalid deposit amount"
    
    def withdraw(self, amount):
        """Withdraw money from the account."""
        if amount > 0 and amount <= self.balance:
            self.balance -= amount
            self.transaction_history.append(f"Withdrew ${amount}")
            return f"Withdrew ${amount}. New balance: ${self.balance}"
        return "Invalid withdrawal amount or insufficient funds"
    
    def get_balance(self):
        """Get current balance."""
        return self.balance
    
    @classmethod
    def get_bank_info(cls):
        """Get bank information (class method)."""
        return f"Bank: {cls.bank_name}, Total Accounts: {cls.total_accounts}"
    
    @staticmethod
    def validate_account_number(account_number):
        """Validate account number format (static method)."""
        return account_number.startswith("ACC") and len(account_number) == 7

# Using the BankAccount class
account1 = BankAccount("Alice", 1000)
account2 = BankAccount("Bob", 500)

print(account1.deposit(200))
print(account1.withdraw(150))
print(BankAccount.get_bank_info())
print(BankAccount.validate_account_number("ACC0001"))
```

## Inheritance and Polymorphism

### Basic Inheritance

```python
class Animal:
    """Base class for all animals."""
    
    def __init__(self, name, species):
        self.name = name
        self.species = species
        self.is_alive = True
    
    def eat(self, food):
        return f"{self.name} is eating {food}"
    
    def sleep(self):
        return f"{self.name} is sleeping"
    
    def make_sound(self):
        return f"{self.name} makes a sound"

class Dog(Animal):
    """Dog class inheriting from Animal."""
    
    def __init__(self, name, breed):
        super().__init__(name, "Canis lupus")  # Call parent constructor
        self.breed = breed
        self.tricks = []
    
    def make_sound(self):  # Override parent method
        return f"{self.name} barks: Woof!"
    
    def learn_trick(self, trick):
        self.tricks.append(trick)
        return f"{self.name} learned {trick}"
    
    def perform_trick(self, trick):
        if trick in self.tricks:
            return f"{self.name} performs {trick}"
        return f"{self.name} doesn't know {trick}"

class Cat(Animal):
    """Cat class inheriting from Animal."""
    
    def __init__(self, name, indoor=True):
        super().__init__(name, "Felis catus")
        self.indoor = indoor
        self.lives = 9
    
    def make_sound(self):  # Override parent method
        return f"{self.name} meows: Meow!"
    
    def climb(self):
        return f"{self.name} climbs gracefully"

# Using inheritance
dog = Dog("Buddy", "Golden Retriever")
cat = Cat("Whiskers", indoor=True)

print(dog.eat("kibble"))      # Inherited method
print(dog.make_sound())       # Overridden method
print(dog.learn_trick("sit")) # Dog-specific method

print(cat.eat("fish"))        # Inherited method
print(cat.make_sound())       # Overridden method
print(cat.climb())            # Cat-specific method
```

### Multiple Inheritance

```python
class Flyable:
    """Mixin class for flying ability."""
    
    def fly(self):
        return f"{self.name} is flying"
    
    def land(self):
        return f"{self.name} has landed"

class Swimmable:
    """Mixin class for swimming ability."""
    
    def swim(self):
        return f"{self.name} is swimming"
    
    def dive(self):
        return f"{self.name} dives underwater"

class Bird(Animal, Flyable):
    """Bird class with flying ability."""
    
    def __init__(self, name, wingspan):
        super().__init__(name, "Aves")
        self.wingspan = wingspan
    
    def make_sound(self):
        return f"{self.name} chirps"

class Duck(Bird, Swimmable):
    """Duck class that can both fly and swim."""
    
    def __init__(self, name):
        super().__init__(name, wingspan=24)  # Average duck wingspan in inches
    
    def make_sound(self):
        return f"{self.name} quacks"

# Using multiple inheritance
duck = Duck("Donald")
print(duck.make_sound())  # Output: Donald quacks
print(duck.fly())         # From Flyable mixin
print(duck.swim())        # From Swimmable mixin
print(duck.eat("bread"))  # From Animal base class

# Method Resolution Order (MRO)
print(Duck.__mro__)  # Shows the order Python searches for methods
```

### Polymorphism

```python
class Shape:
    """Base class for geometric shapes."""
    
    def __init__(self, name):
        self.name = name
    
    def area(self):
        """Calculate area - to be overridden by subclasses."""
        raise NotImplementedError("Subclass must implement area method")
    
    def perimeter(self):
        """Calculate perimeter - to be overridden by subclasses."""
        raise NotImplementedError("Subclass must implement perimeter method")
    
    def describe(self):
        """Describe the shape."""
        return f"This is a {self.name}"

class Rectangle(Shape):
    """Rectangle shape."""
    
    def __init__(self, width, height):
        super().__init__("Rectangle")
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height
    
    def perimeter(self):
        return 2 * (self.width + self.height)

class Circle(Shape):
    """Circle shape."""
    
    def __init__(self, radius):
        super().__init__("Circle")
        self.radius = radius
    
    def area(self):
        return 3.14159 * self.radius ** 2
    
    def perimeter(self):
        return 2 * 3.14159 * self.radius

class Triangle(Shape):
    """Triangle shape."""
    
    def __init__(self, side1, side2, side3):
        super().__init__("Triangle")
        self.side1 = side1
        self.side2 = side2
        self.side3 = side3
    
    def area(self):
        # Using Heron's formula
        s = self.perimeter() / 2
        return (s * (s - self.side1) * (s - self.side2) * (s - self.side3)) ** 0.5
    
    def perimeter(self):
        return self.side1 + self.side2 + self.side3

# Polymorphism in action
shapes = [
    Rectangle(5, 4),
    Circle(3),
    Triangle(3, 4, 5)
]

# Same method calls work on different object types
for shape in shapes:
    print(f"{shape.describe()}")
    print(f"Area: {shape.area():.2f}")
    print(f"Perimeter: {shape.perimeter():.2f}")
    print("-" * 30)
```

## Encapsulation and Data Hiding

### Private and Protected Attributes

```python
class BankAccount:
    """Demonstrates encapsulation with private attributes."""
    
    def __init__(self, account_holder, initial_balance=0):
        self.account_holder = account_holder  # Public
        self._account_number = self._generate_account_number()  # Protected
        self.__balance = initial_balance  # Private
        self.__pin = None  # Private
    
    def _generate_account_number(self):
        """Protected method - internal use."""
        import random
        return f"ACC{random.randint(10000, 99999)}"
    
    def __validate_transaction(self, amount):
        """Private method - internal validation."""
        return isinstance(amount, (int, float)) and amount > 0
    
    def set_pin(self, pin):
        """Set account PIN."""
        if len(str(pin)) == 4:
            self.__pin = pin
            return "PIN set successfully"
        return "PIN must be 4 digits"
    
    def deposit(self, amount, pin=None):
        """Deposit money with optional PIN verification."""
        if not self.__validate_transaction(amount):
            return "Invalid amount"
        
        if self.__pin and pin != self.__pin:
            return "Invalid PIN"
        
        self.__balance += amount
        return f"Deposited ${amount}. New balance: ${self.__balance}"
    
    def withdraw(self, amount, pin):
        """Withdraw money with PIN verification."""
        if not self.__validate_transaction(amount):
            return "Invalid amount"
        
        if pin != self.__pin:
            return "Invalid PIN"
        
        if amount > self.__balance:
            return "Insufficient funds"
        
        self.__balance -= amount
        return f"Withdrew ${amount}. New balance: ${self.__balance}"
    
    def get_balance(self, pin):
        """Get balance with PIN verification."""
        if pin != self.__pin:
            return "Invalid PIN"
        return self.__balance
    
    @property
    def account_info(self):
        """Get public account information."""
        return {
            "holder": self.account_holder,
            "account_number": self._account_number
        }

# Using encapsulation
account = BankAccount("Alice", 1000)

# Public access
print(account.account_holder)  # Works
print(account.account_info)    # Works

# Protected access (by convention, shouldn't be used externally)
print(account._account_number)  # Works but not recommended

# Private access (name mangling makes it harder to access)
# print(account.__balance)  # AttributeError

# Proper way to access private data
account.set_pin(1234)
print(account.get_balance(1234))  # Output: 1000
print(account.withdraw(200, 1234))  # Output: Withdrew $200. New balance: $800
```

## Special Methods and Properties

### Magic Methods (Dunder Methods)

```python
class Vector:
    """A 2D vector class demonstrating special methods."""
    
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __str__(self):
        """String representation for users."""
        return f"Vector({self.x}, {self.y})"
    
    def __repr__(self):
        """String representation for developers."""
        return f"Vector(x={self.x}, y={self.y})"
    
    def __add__(self, other):
        """Add two vectors."""
        if isinstance(other, Vector):
            return Vector(self.x + other.x, self.y + other.y)
        return NotImplemented
    
    def __sub__(self, other):
        """Subtract two vectors."""
        if isinstance(other, Vector):
            return Vector(self.x - other.x, self.y - other.y)
        return NotImplemented
    
    def __mul__(self, scalar):
        """Multiply vector by scalar."""
        if isinstance(scalar, (int, float)):
            return Vector(self.x * scalar, self.y * scalar)
        return NotImplemented
    
    def __rmul__(self, scalar):
        """Right multiplication (scalar * vector)."""
        return self.__mul__(scalar)
    
    def __eq__(self, other):
        """Check equality."""
        if isinstance(other, Vector):
            return self.x == other.x and self.y == other.y
        return False
    
    def __lt__(self, other):
        """Less than comparison (by magnitude)."""
        if isinstance(other, Vector):
            return self.magnitude() < other.magnitude()
        return NotImplemented
    
    def __len__(self):
        """Return magnitude as length."""
        return int(self.magnitude())
    
    def __getitem__(self, index):
        """Allow indexing."""
        if index == 0:
            return self.x
        elif index == 1:
            return self.y
        else:
            raise IndexError("Vector index out of range")
    
    def __setitem__(self, index, value):
        """Allow item assignment."""
        if index == 0:
            self.x = value
        elif index == 1:
            self.y = value
        else:
            raise IndexError("Vector index out of range")
    
    def magnitude(self):
        """Calculate vector magnitude."""
        return (self.x ** 2 + self.y ** 2) ** 0.5
    
    def normalize(self):
        """Return normalized vector."""
        mag = self.magnitude()
        if mag == 0:
            return Vector(0, 0)
        return Vector(self.x / mag, self.y / mag)

# Using special methods
v1 = Vector(3, 4)
v2 = Vector(1, 2)

print(v1)           # Output: Vector(3, 4) (uses __str__)
print(repr(v1))     # Output: Vector(x=3, y=4) (uses __repr__)

# Arithmetic operations
v3 = v1 + v2        # Uses __add__
print(v3)           # Output: Vector(4, 6)

v4 = v1 * 2         # Uses __mul__
print(v4)           # Output: Vector(6, 8)

v5 = 3 * v1         # Uses __rmul__
print(v5)           # Output: Vector(9, 12)

# Comparison operations
print(v1 == v2)     # Output: False (uses __eq__)
print(v1 < v2)      # Output: False (uses __lt__)

# Length and indexing
print(len(v1))      # Output: 5 (uses __len__)
print(v1[0])        # Output: 3 (uses __getitem__)
v1[1] = 5           # Uses __setitem__
print(v1)           # Output: Vector(3, 5)
```

### Properties and Descriptors

```python
class Temperature:
    """A class for temperature conversion with properties."""
    
    def __init__(self, celsius=0):
        """Initialize with Celsius temperature."""
        self._celsius = celsius
    
    @property
    def celsius(self):
        """Get temperature in Celsius."""
        return self._celsius
    
    @celsius.setter
    def celsius(self, value):
        """Set temperature in Celsius with validation."""
        if value < -273.15:
            raise ValueError("Temperature cannot be below absolute zero")
        self._celsius = value
    
    @property
    def fahrenheit(self):
        """Get temperature in Fahrenheit."""
        return (self._celsius * 9/5) + 32
    
    @fahrenheit.setter
    def fahrenheit(self, value):
        """Set temperature using Fahrenheit."""
        self.celsius = (value - 32) * 5/9
    
    @property
    def kelvin(self):
        """Get temperature in Kelvin."""
        return self._celsius + 273.15
    
    @kelvin.setter
    def kelvin(self, value):
        """Set temperature using Kelvin."""
        self.celsius = value - 273.15
    
    def __str__(self):
        """String representation of temperature."""
        return f"{self._celsius}°C ({self.fahrenheit}°F, {self.kelvin}K)"

# Using properties
temp = Temperature(25)
print(temp)  # Output: 25°C (77.0°F, 298.15K)

temp.fahrenheit = 100
print(temp)  # Output: 37.77777777777778°C (100.0°F, 310.92777777777775K)

temp.kelvin = 300
print(temp)  # Output: 26.850000000000023°C (80.33000000000004°F, 300K)
```

## Practice Exercise - Complete OOP System

```python
class Library:
    """A complete library management system demonstrating OOP principles."""
    
    def __init__(self, name):
        self.name = name
        self._books = []
        self._members = []
        self._borrowed_books = {}
    
    def add_book(self, book):
        """Add a book to the library."""
        self._books.append(book)
        return f"Added '{book.title}' to {self.name}"
    
    def add_member(self, member):
        """Add a member to the library."""
        self._members.append(member)
        return f"Added member: {member.name}"
    
    def borrow_book(self, member, book_title):
        """Allow a member to borrow a book."""
        book = self._find_book(book_title)
        if not book:
            return f"Book '{book_title}' not found"
        
        if book.is_available:
            book.borrow()
            if member.member_id not in self._borrowed_books:
                self._borrowed_books[member.member_id] = []
            self._borrowed_books[member.member_id].append(book)
            return f"{member.name} borrowed '{book.title}'"
        else:
            return f"'{book.title}' is not available"
    
    def return_book(self, member, book_title):
        """Allow a member to return a book."""
        if member.member_id in self._borrowed_books:
            for book in self._borrowed_books[member.member_id]:
                if book.title == book_title:
                    book.return_book()
                    self._borrowed_books[member.member_id].remove(book)
                    return f"{member.name} returned '{book.title}'"
        return f"Book '{book_title}' was not borrowed by {member.name}"
    
    def _find_book(self, title):
        """Private method to find a book by title."""
        for book in self._books:
            if book.title.lower() == title.lower():
                return book
        return None
    
    def get_available_books(self):
        """Get list of available books."""
        return [book for book in self._books if book.is_available]
    
    def __str__(self):
        return f"Library: {self.name} ({len(self._books)} books, {len(self._members)} members)"

class Book:
    """Book class with encapsulation."""
    
    def __init__(self, title, author, isbn):
        self.title = title
        self.author = author
        self.isbn = isbn
        self._is_available = True
        self._borrow_count = 0
    
    @property
    def is_available(self):
        return self._is_available
    
    def borrow(self):
        """Mark book as borrowed."""
        if self._is_available:
            self._is_available = False
            self._borrow_count += 1
            return True
        return False
    
    def return_book(self):
        """Mark book as returned."""
        self._is_available = True
    
    def __str__(self):
        status = "Available" if self._is_available else "Borrowed"
        return f"'{self.title}' by {self.author} - {status}"
    
    def __eq__(self, other):
        if isinstance(other, Book):
            return self.isbn == other.isbn
        return False

class Member:
    """Library member class."""
    
    _next_id = 1
    
    def __init__(self, name, email):
        self.name = name
        self.email = email
        self.member_id = Member._next_id
        Member._next_id += 1
        self._join_date = "2024-01-01"  # Simplified
    
    def __str__(self):
        return f"Member: {self.name} (ID: {self.member_id})"

# Using the complete OOP system
library = Library("City Library")

# Create books
book1 = Book("Python Programming", "John Doe", "978-1234567890")
book2 = Book("Data Science Handbook", "Jane Smith", "978-0987654321")
book3 = Book("Web Development", "Bob Johnson", "978-1122334455")

# Create members
member1 = Member("Alice Brown", "alice@email.com")
member2 = Member("Charlie Davis", "charlie@email.com")

# Add books and members to library
library.add_book(book1)
library.add_book(book2)
library.add_book(book3)
library.add_member(member1)
library.add_member(member2)

print(library)

# Borrow and return books
print(library.borrow_book(member1, "Python Programming"))
print(library.borrow_book(member2, "Python Programming"))  # Should fail
print(library.return_book(member1, "Python Programming"))
print(library.borrow_book(member2, "Python Programming"))  # Should work now

# Display available books
available = library.get_available_books()
print(f"\nAvailable books: {len(available)}")
for book in available:
    print(f"  {book}")
```

## Key Takeaways

- Classes define blueprints for objects with attributes and methods
- Inheritance allows classes to inherit and extend functionality from parent classes
- Polymorphism enables different classes to be used interchangeably through common interfaces
- Encapsulation hides internal implementation details and protects data integrity
- Special methods enable custom behavior for built-in operations
- Use `@property` decorators for controlled attribute access
- Multiple inheritance should be used carefully with mixin classes
- Follow naming conventions: public, _protected, __private

## What's Next?

Now that you understand object-oriented programming, you're ready to explore Python's advanced features like decorators, generators, and context managers. Let's move on to [Advanced Features](11-advanced-features.md)!