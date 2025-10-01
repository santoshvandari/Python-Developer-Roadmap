# Number Guessing Game Project

Build an interactive number guessing game where players try to guess a randomly generated number.

## Project Overview

**What you'll build**: A fun guessing game where the computer generates a random number and the player tries to guess it with hints and scoring.

**What you'll learn**:
- Random number generation
- While loops and loop control
- Conditional statements and logic
- User input validation
- Game state management
- Basic file operations for high scores

## Project Features

### Basic Features
- Generate random numbers in a specified range
- Accept user guesses and provide feedback
- Track number of attempts
- Declare winner when correct guess is made
- Play again functionality

### Advanced Features
- Multiple difficulty levels
- High score tracking
- Hint system based on guesses
- Achievement system
- Statistics tracking across games

## Implementation Guide

### Phase 1: Basic Game
**Time**: 1-2 hours

Create a simple guessing game:
- Generate random number between 1-100
- Accept user guesses
- Provide "too high" or "too low" feedback
- Count attempts and announce winner

**Key concepts**: Random numbers, loops, conditionals

### Phase 2: Enhanced Game
**Time**: 2-3 hours

Add difficulty levels and validation:
- Easy (1-50), Medium (1-100), Hard (1-500) modes
- Input validation for invalid entries
- Limited attempts based on difficulty
- Better user interface and feedback

**Key concepts**: Functions, input validation, game logic

### Phase 3: Advanced Features
**Time**: 3-4 hours

Implement scoring and persistence:
- Score calculation based on attempts and difficulty
- High score tracking with file storage
- Game statistics (games played, win rate)
- Hint system for struggling players

**Key concepts**: File operations, data persistence, algorithms

### Phase 4: GUI Version
**Time**: 4-5 hours

Create a graphical interface:
- Number input field and guess button
- Visual feedback and game status
- Difficulty selection and settings
- Statistics display and high scores

**Key concepts**: GUI programming, event handling

## Getting Started

### Setup
1. Create a new Python file for your game
2. Import the random module
3. Plan your game flow and functions

### Basic Structure
```python
import random

def generate_number(min_val=1, max_val=100):
    return random.randint(min_val, max_val)

def get_user_guess():
    while True:
        try:
            guess = int(input("Enter your guess: "))
            return guess
        except ValueError:
            print("Please enter a valid number!")

def play_game():
    # Main game logic here
    pass

if __name__ == "__main__":
    play_game()
```

## Game Logic Implementation

### Main Game Loop
```python
def play_game():
    print("Welcome to the Number Guessing Game!")
    
    # Choose difficulty
    difficulty = choose_difficulty()
    min_num, max_num, max_attempts = get_difficulty_settings(difficulty)
    
    # Generate secret number
    secret_number = random.randint(min_num, max_num)
    attempts = 0
    
    print(f"I'm thinking of a number between {min_num} and {max_num}")
    print(f"You have {max_attempts} attempts to guess it!")
    
    while attempts < max_attempts:
        guess = get_user_guess()
        attempts += 1
        
        if guess == secret_number:
            print(f"Congratulations! You guessed it in {attempts} attempts!")
            break
        elif guess < secret_number:
            print("Too low! Try again.")
        else:
            print("Too high! Try again.")
    
    else:
        print(f"Game over! The number was {secret_number}")
```

### Difficulty Settings
```python
def choose_difficulty():
    print("\nChoose difficulty:")
    print("1. Easy (1-50, 10 attempts)")
    print("2. Medium (1-100, 7 attempts)")
    print("3. Hard (1-500, 12 attempts)")
    
    while True:
        choice = input("Enter your choice (1-3): ")
        if choice in ['1', '2', '3']:
            return int(choice)
        print("Please enter 1, 2, or 3")

def get_difficulty_settings(difficulty):
    settings = {
        1: (1, 50, 10),    # Easy
        2: (1, 100, 7),    # Medium
        3: (1, 500, 12)    # Hard
    }
    return settings[difficulty]
```

## Score and Statistics

### Score Calculation
```python
def calculate_score(attempts, max_attempts, difficulty):
    # Base score depends on difficulty
    base_scores = {1: 100, 2: 200, 3: 500}
    base_score = base_scores[difficulty]
    
    # Bonus for fewer attempts
    attempt_bonus = max(0, (max_attempts - attempts) * 10)
    
    return base_score + attempt_bonus
```

### High Score Tracking
```python
import json

def save_high_score(score, difficulty):
    try:
        with open('high_scores.json', 'r') as f:
            scores = json.load(f)
    except FileNotFoundError:
        scores = {'easy': 0, 'medium': 0, 'hard': 0}
    
    difficulty_names = {1: 'easy', 2: 'medium', 3: 'hard'}
    difficulty_name = difficulty_names[difficulty]
    
    if score > scores[difficulty_name]:
        scores[difficulty_name] = score
        print(f"New high score for {difficulty_name} difficulty: {score}!")
        
        with open('high_scores.json', 'w') as f:
            json.dump(scores, f)
        return True
    return False
```

## Testing Your Game

### Test Scenarios
- Play through each difficulty level
- Test edge cases (minimum and maximum numbers)
- Test invalid inputs (letters, negative numbers)
- Test winning on first guess vs. using all attempts
- Verify score calculation and high score saving

### Input Validation
- Handle non-numeric input gracefully
- Ensure guesses are within the valid range
- Provide clear error messages

## Extensions and Improvements

### Beginner Extensions
- Add a hint system (show if guess is within 10 of the target)
- Create themed versions (guess the age, price, etc.)
- Add sound effects for correct/incorrect guesses
- Implement a simple AI that tries to guess your number

### Intermediate Extensions
- Multiplayer mode (players take turns)
- Tournament system with multiple rounds
- Different number types (decimals, negative numbers)
- Word guessing variation

### Advanced Extensions
- Machine learning to analyze player patterns
- Web-based version with leaderboards
- Mobile app version
- Voice recognition for guesses

## Learning Outcomes

After completing this project, you'll understand:
- How to generate and work with random numbers
- Loop control and conditional logic
- Input validation and error handling
- File operations for data persistence
- Basic game development principles
- User interface design

## File Structure

```
number_guessing_game/
├── basic_game.py          # Phase 1 simple version
├── enhanced_game.py       # Phase 2 with difficulty
├── advanced_game.py       # Phase 3 with scores
├── gui_game.py           # Phase 4 GUI version
├── high_scores.json      # High score data
└── README.md             # Project documentation
```

## Next Steps

Once you've completed your guessing game:
1. Challenge friends and family to beat your high scores
2. Add your own creative features and themes
3. Try implementing the AI guesser version
4. Move on to the Password Generator project
5. Share your game and get feedback from others

Great work on building an entertaining and educational game!