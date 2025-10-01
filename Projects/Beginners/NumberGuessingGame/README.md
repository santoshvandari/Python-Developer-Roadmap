# 🎯 Number Guessing Game

<div align="center">
  <img src="https://cdn-icons-png.flaticon.com/512/2995/2995467.png" alt="Number Guessing Game" width="200"/>
  <p><strong>Build an interactive number guessing game with multiple difficulty levels</strong></p>
</div>

---
-
## 🎯 Project Overview

Create a fun and interactive number guessing game where the computer generates a random number and the player tries to guess it. This project will teach you about loops, conditionals, random number generation, and user interaction.

### What You'll Learn
- Random number generation
- While loops and loop control
- Conditional statements (if/elif/else)
- User input validation
- Game logic and state management
- File operations for high scores
- Basic algorithm optimization

### Prerequisites
Before starting this project, you should understand:
- [Control Structures](../../Roadmap/06-control-structures.md) - Loops and conditionals
- [Input/Output](../../Roadmap/05-input-output.md) - Getting user input
- [Data Types](../../Roadmap/03-data-types.md) - Numbers and strings
- [Functions](../../Roadmap/07-functions.md) - Creating reusable code

## 📋 Project Phases

### Phase 1: Basic Game (⭐)
**Time**: 1-2 hours | **Concepts**: Random numbers, loops, conditionals

Create a simple guessing game with basic functionality.

### Phase 2: Enhanced Game (⭐⭐)
**Time**: 2-3 hours | **Concepts**: Functions, input validation, game statistics

Add difficulty levels, input validation, and attempt tracking.

### Phase 3: Advanced Features (⭐⭐⭐)
**Time**: 3-4 hours | **Concepts**: File handling, data persistence, advanced features

Implement high scores, hints, and multiple game modes.

### Phase 4: GUI Version (⭐⭐⭐⭐)
**Time**: 4-5 hours | **Concepts**: GUI programming, event handling

Create a graphical interface version of the game.

---

## 🚀 Phase 1: Basic Number Guessing Game

### Learning Objectives
- Use the `random` module to generate random numbers
- Implement while loops for game continuation
- Use conditional statements for game logic
- Handle user input and provide feedback

### Step-by-Step Implementation

#### Step 1: Import required modules and set up the game

```python
# basic_guessing_game.py

import random

print("Welcome to the Number Guessing Game! 🎯")
print("I'm thinking of a number between 1 and 100.")
print("Can you guess what it is?")
print("-" * 40)

# Generate random number
secret_number = random.randint(1, 100)
attempts = 0
max_attempts = 10

print(f"You have {max_attempts} attempts to guess the number.")
print("Let's start!")
```

#### Step 2: Implement the main game loop

```python
# basic_guessing_game.py (continued)

while attempts < max_attempts:
    try:
        # Get user input
        guess = int(input(f"\nAttempt {attempts + 1}: Enter your guess (1-100): "))
        attempts += 1
        
        # Check if guess is in valid range
        if guess < 1 or guess > 100:
            print("Please enter a number between 1 and 100!")
            continue
        
        # Check the guess
        if guess == secret_number:
            print(f"\n🎉 Congratulations! You guessed it!")
            print(f"The number was {secret_number}")
            print(f"You won in {attempts} attempts!")
            break
        elif guess < secret_number:
            print("📈 Too low! Try a higher number.")
        else:
            print("📉 Too high! Try a lower number.")
        
        # Show remaining attempts
        remaining = max_attempts - attempts
        if remaining > 0:
            print(f"You have {remaining} attempts left.")
        
    except ValueError:
        print("❌ Please enter a valid number!")
        # Don't count invalid input as an attempt
        continue

# Game over - check if player won or lost
if attempts >= max_attempts and guess != secret_number:
    print(f"\n💔 Game Over! You've used all {max_attempts} attempts.")
    print(f"The number was {secret_number}. Better luck next time!")

print("\nThanks for playing! 👋")
```

#### Step 3: Test your basic game

Run the program and test different scenarios:
```bash
python basic_guessing_game.py
```

**Test cases to try:**
- Correct guess on first try
- Guess that's too high
- Guess that's too low
- Invalid input (letters, negative numbers)
- Using all attempts without winning

---

## 🔧 Phase 2: Enhanced Number Guessing Game

### Learning Objectives
- Organize code using functions
- Implement multiple difficulty levels
- Add input validation and error handling
- Track and display game statistics
- Implement play-again functionality

### Implementation

```python
# enhanced_guessing_game.py

import random
import time

class NumberGuessingGame:
    def __init__(self):
        self.difficulties = {
            'easy': {'range': (1, 50), 'attempts': 15, 'name': 'Easy'},
            'medium': {'range': (1, 100), 'attempts': 10, 'name': 'Medium'}, 
            'hard': {'range': (1, 200), 'attempts': 8, 'name': 'Hard'},
            'expert': {'range': (1, 500), 'attempts': 12, 'name': 'Expert'}
        }
        self.stats = {
            'games_played': 0,
            'games_won': 0,
            'total_attempts': 0,
            'best_score': {'attempts': float('inf'), 'difficulty': None}
        }
    
    def display_welcome(self):
        """Display welcome message and game rules"""
        print("=" * 60)
        print("🎯 ENHANCED NUMBER GUESSING GAME 🎯".center(60))
        print("=" * 60)
        print()
        print("How to play:")
        print("• I'll think of a number within the chosen range")
        print("• You guess the number")
        print("• I'll tell you if your guess is too high or too low")
        print("• Try to guess in as few attempts as possible!")
        print()
    
    def choose_difficulty(self):
        """Let player choose difficulty level"""
        print("Choose your difficulty level:")
        print()
        
        for key, value in self.difficulties.items():
            min_num, max_num = value['range']
            attempts = value['attempts']
            name = value['name']
            print(f"{key[0].upper()}. {name}: {min_num}-{max_num} ({attempts} attempts)")
        
        while True:
            choice = input("\nEnter your choice (e/m/h/x): ").lower()
            
            if choice == 'e':
                return 'easy'
            elif choice == 'm':
                return 'medium'
            elif choice == 'h':
                return 'hard'
            elif choice == 'x':
                return 'expert'
            else:
                print("❌ Invalid choice! Please enter e, m, h, or x.")
    
    def get_valid_guess(self, min_num, max_num, attempt_num):
        """Get a valid guess from the player"""
        while True:
            try:
                prompt = f"\nAttempt {attempt_num}: Guess the number ({min_num}-{max_num}): "
                guess = int(input(prompt))
                
                if min_num <= guess <= max_num:
                    return guess
                else:
                    print(f"❌ Please enter a number between {min_num} and {max_num}!")
            
            except ValueError:
                print("❌ Please enter a valid number!")
    
    def give_hint(self, guess, secret_number, min_num, max_num):
        """Provide helpful hints based on the guess"""
        difference = abs(guess - secret_number)
        range_size = max_num - min_num
        
        if difference <= range_size * 0.05:  # Very close (within 5% of range)
            return "🔥 You're burning hot! Very close!"
        elif difference <= range_size * 0.15:  # Close (within 15% of range)
            return "♨️ You're getting warm!"
        elif difference <= range_size * 0.30:  # Moderate (within 30% of range)
            return "🌡️ You're getting closer..."
        else:
            return "🧊 You're cold. Try a different direction!"
    
    def calculate_score(self, attempts, max_attempts, difficulty):
        """Calculate score based on attempts and difficulty"""
        base_score = 1000
        difficulty_multiplier = {'easy': 1, 'medium': 1.5, 'hard': 2, 'expert': 3}
        
        # Bonus for using fewer attempts
        attempt_bonus = (max_attempts - attempts) * 50
        
        # Difficulty bonus
        diff_bonus = base_score * (difficulty_multiplier[difficulty] - 1)
        
        return int(base_score + attempt_bonus + diff_bonus)
    
    def play_round(self):
        """Play a single round of the game"""
        self.stats['games_played'] += 1
        
        # Choose difficulty
        difficulty = self.choose_difficulty()
        settings = self.difficulties[difficulty]
        min_num, max_num = settings['range']
        max_attempts = settings['attempts']
        
        print(f"\n🎮 Starting {settings['name']} mode!")
        print(f"Number range: {min_num} to {max_num}")
        print(f"Maximum attempts: {max_attempts}")
        print("-" * 40)
        
        # Generate secret number
        secret_number = random.randint(min_num, max_num)
        attempts = 0
        
        # Game loop
        while attempts < max_attempts:
            guess = self.get_valid_guess(min_num, max_num, attempts + 1)
            attempts += 1
            
            if guess == secret_number:
                # Player wins!
                print(f"\n🎉 CONGRATULATIONS! 🎉")
                print(f"You guessed the number {secret_number} correctly!")
                print(f"It took you {attempts} attempts.")
                
                # Calculate and show score
                score = self.calculate_score(attempts, max_attempts, difficulty)
                print(f"Your score: {score} points")
                
                # Update statistics
                self.stats['games_won'] += 1
                self.stats['total_attempts'] += attempts
                
                # Check for best score
                if attempts < self.stats['best_score']['attempts']:
                    self.stats['best_score']['attempts'] = attempts
                    self.stats['best_score']['difficulty'] = difficulty
                    print("🏆 NEW PERSONAL BEST!")
                
                return True
            
            else:
                # Provide feedback
                if guess < secret_number:
                    print("📈 Too low!")
                else:
                    print("📉 Too high!")
                
                # Give hint (except on last attempt)
                remaining = max_attempts - attempts
                if remaining > 0:
                    hint = self.give_hint(guess, secret_number, min_num, max_num)
                    print(hint)
                    print(f"Attempts remaining: {remaining}")
        
        # Player lost
        print(f"\n💔 Game Over!")
        print(f"You've used all {max_attempts} attempts.")
        print(f"The number was {secret_number}.")
        print("Better luck next time!")
        
        self.stats['total_attempts'] += attempts
        return False
    
    def show_statistics(self):
        """Display player statistics"""
        if self.stats['games_played'] == 0:
            print("No games played yet!")
            return
        
        print("\n📊 YOUR STATISTICS")
        print("=" * 30)
        print(f"Games played: {self.stats['games_played']}")
        print(f"Games won: {self.stats['games_won']}")
        
        win_rate = (self.stats['games_won'] / self.stats['games_played']) * 100
        print(f"Win rate: {win_rate:.1f}%")
        
        if self.stats['games_won'] > 0:
            avg_attempts = self.stats['total_attempts'] / self.stats['games_won']
            print(f"Average attempts per win: {avg_attempts:.1f}")
        
        if self.stats['best_score']['attempts'] != float('inf'):
            best_attempts = self.stats['best_score']['attempts']
            best_difficulty = self.stats['best_score']['difficulty']
            print(f"Best score: {best_attempts} attempts ({best_difficulty} mode)")
    
    def play_again(self):
        """Ask if player wants to play again"""
        while True:
            choice = input("\nWould you like to play again? (y/n): ").lower()
            if choice in ['y', 'yes']:
                return True
            elif choice in ['n', 'no']:
                return False
            else:
                print("Please enter 'y' for yes or 'n' for no.")
    
    def run(self):
        """Main game loop"""
        self.display_welcome()
        
        while True:
            self.play_round()
            self.show_statistics()
            
            if not self.play_again():
                break
        
        print("\n🎯 Thanks for playing the Number Guessing Game!")
        print("Hope you had fun! 👋")

if __name__ == "__main__":
    game = NumberGuessingGame()
    game.run()
```

---

## 💾 Phase 3: Advanced Features with Persistence

### Learning Objectives
- Implement file operations for data persistence
- Add high score tracking across sessions
- Create multiple game modes
- Implement achievement system
- Add game replay and analysis features

### Implementation

```python
# advanced_guessing_game.py

import random
import json
import os
from datetime import datetime
import time

class AdvancedGuessingGame:
    def __init__(self):
        self.data_file = "game_data.json"
        self.difficulties = {
            'easy': {'range': (1, 50), 'attempts': 15, 'name': 'Easy'},
            'medium': {'range': (1, 100), 'attempts': 10, 'name': 'Medium'}, 
            'hard': {'range': (1, 200), 'attempts': 8, 'name': 'Hard'},
            'expert': {'range': (1, 500), 'attempts': 12, 'name': 'Expert'},
            'custom': {'range': None, 'attempts': None, 'name': 'Custom'}
        }
        
        self.achievements = {
            'first_win': {'name': 'First Victory', 'desc': 'Win your first game', 'unlocked': False},
            'perfectionist': {'name': 'Perfectionist', 'desc': 'Win in 3 attempts or less', 'unlocked': False},
            'persistent': {'name': 'Persistent', 'desc': 'Play 10 games', 'unlocked': False},
            'lucky_streak': {'name': 'Lucky Streak', 'desc': 'Win 3 games in a row', 'unlocked': False},
            'expert_player': {'name': 'Expert Player', 'desc': 'Win on Expert difficulty', 'unlocked': False}
        }
        
        self.load_data()
    
    def load_data(self):
        """Load game data from file"""
        try:
            if os.path.exists(self.data_file):
                with open(self.data_file, 'r') as f:
                    data = json.load(f)
                    self.stats = data.get('stats', self.get_default_stats())
                    self.high_scores = data.get('high_scores', [])
                    self.achievements = {**self.achievements, **data.get('achievements', {})}
                    self.game_history = data.get('game_history', [])
            else:
                self.stats = self.get_default_stats()
                self.high_scores = []
                self.game_history = []
        except Exception as e:
            print(f"Warning: Could not load game data - {e}")
            self.stats = self.get_default_stats()
            self.high_scores = []
            self.game_history = []
    
    def save_data(self):
        """Save game data to file"""
        try:
            data = {
                'stats': self.stats,
                'high_scores': self.high_scores,
                'achievements': self.achievements,
                'game_history': self.game_history
            }
            with open(self.data_file, 'w') as f:
                json.dump(data, f, indent=2)
        except Exception as e:
            print(f"Warning: Could not save game data - {e}")
    
    def get_default_stats(self):
        """Return default statistics"""
        return {
            'games_played': 0,
            'games_won': 0,
            'total_attempts': 0,
            'win_streak': 0,
            'best_streak': 0,
            'total_score': 0,
            'difficulty_wins': {'easy': 0, 'medium': 0, 'hard': 0, 'expert': 0, 'custom': 0}
        }
    
    def display_main_menu(self):
        """Display main menu"""
        print("\\n" + "=" * 60)
        print("🎯 ADVANCED NUMBER GUESSING GAME 🎯".center(60))
        print("=" * 60)
        print("1. 🎮 Play Game")
        print("2. 📊 View Statistics") 
        print("3. 🏆 High Scores")
        print("4. 🎖️ Achievements")
        print("5. 📈 Game History")
        print("6. ⚙️ Custom Game")
        print("7. ❓ How to Play")
        print("8. 🚪 Exit")
        print("=" * 60)
    
    def custom_game_setup(self):
        """Set up custom game parameters"""
        print("\\n🛠️ CUSTOM GAME SETUP")
        print("-" * 30)
        
        # Get custom range
        while True:
            try:
                min_num = int(input("Enter minimum number: "))
                max_num = int(input("Enter maximum number: "))
                
                if min_num >= max_num:
                    print("❌ Maximum must be greater than minimum!")
                    continue
                
                range_size = max_num - min_num + 1
                if range_size < 2:
                    print("❌ Range must contain at least 2 numbers!")
                    continue
                
                break
            except ValueError:
                print("❌ Please enter valid numbers!")
        
        # Calculate suggested attempts
        suggested_attempts = max(5, int(range_size ** 0.5) + 3)
        
        while True:
            try:
                print(f"\\nSuggested attempts for this range: {suggested_attempts}")
                attempts = int(input("Enter maximum attempts: "))
                
                if attempts < 1:
                    print("❌ Must have at least 1 attempt!")
                    continue
                
                break
            except ValueError:
                print("❌ Please enter a valid number!")
        
        return {'range': (min_num, max_num), 'attempts': attempts, 'name': 'Custom'}
    
    def play_game_mode(self):
        """Handle game mode selection and play"""
        print("\\n🎮 GAME MODES")
        print("-" * 20)
        
        for key, value in self.difficulties.items():
            if key == 'custom':
                print(f"{key[0].upper()}. {value['name']}: Create your own challenge")
            else:
                min_num, max_num = value['range']
                attempts = value['attempts']
                print(f"{key[0].upper()}. {value['name']}: {min_num}-{max_num} ({attempts} attempts)")
        
        while True:
            choice = input("\\nChoose game mode (e/m/h/x/c): ").lower()
            
            if choice in ['e', 'm', 'h', 'x']:
                difficulty_map = {'e': 'easy', 'm': 'medium', 'h': 'hard', 'x': 'expert'}
                return self.play_round(difficulty_map[choice])
            elif choice == 'c':
                custom_settings = self.custom_game_setup()
                return self.play_round('custom', custom_settings)
            else:
                print("❌ Invalid choice!")
    
    def play_round(self, difficulty, custom_settings=None):
        """Play a single round"""
        if difficulty == 'custom':
            settings = custom_settings
        else:
            settings = self.difficulties[difficulty]
        
        min_num, max_num = settings['range']
        max_attempts = settings['attempts']
        
        print(f"\\n🎮 {settings['name']} Mode")
        print(f"Range: {min_num} to {max_num}")
        print(f"Max attempts: {max_attempts}")
        print("-" * 40)
        
        secret_number = random.randint(min_num, max_num)
        attempts = 0
        start_time = time.time()
        guess_history = []
        
        while attempts < max_attempts:
            guess = self.get_valid_guess(min_num, max_num, attempts + 1)
            attempts += 1
            guess_history.append(guess)
            
            if guess == secret_number:
                end_time = time.time()
                game_time = end_time - start_time
                
                print(f"\\n🎉 VICTORY! 🎉")
                print(f"Number: {secret_number}")
                print(f"Attempts: {attempts}")
                print(f"Time: {game_time:.1f} seconds")
                
                score = self.calculate_score(attempts, max_attempts, difficulty, game_time)
                print(f"Score: {score}")
                
                self.update_stats_win(attempts, difficulty, score, game_time, guess_history, secret_number)
                return True
            
            else:
                feedback = "📈 Too low!" if guess < secret_number else "📉 Too high!"
                print(feedback)
                
                remaining = max_attempts - attempts
                if remaining > 0:
                    hint = self.get_smart_hint(guess_history, secret_number, min_num, max_num)
                    print(hint)
                    print(f"Remaining: {remaining}")
        
        # Game lost
        end_time = time.time()
        game_time = end_time - start_time
        print(f"\\n💔 Game Over! Number was {secret_number}")
        
        self.update_stats_loss(attempts, difficulty, game_time, guess_history, secret_number)
        return False
    
    def get_smart_hint(self, guess_history, secret_number, min_num, max_num):
        """Provide intelligent hints based on guess history"""
        last_guess = guess_history[-1]
        difference = abs(last_guess - secret_number)
        range_size = max_num - min_num
        
        # Analyze guess pattern
        if len(guess_history) >= 2:
            prev_diff = abs(guess_history[-2] - secret_number)
            if difference < prev_diff:
                trend = "🎯 Getting warmer!"
            elif difference > prev_diff:
                trend = "❄️ Getting colder!"
            else:
                trend = "↔️ Same distance..."
        else:
            trend = ""
        
        # Distance hint
        if difference <= range_size * 0.05:
            distance = "🔥 Burning hot!"
        elif difference <= range_size * 0.15:
            distance = "♨️ Very warm!"
        elif difference <= range_size * 0.30:
            distance = "🌡️ Warm..."
        elif difference <= range_size * 0.50:
            distance = "🧊 Cool."
        else:
            distance = "🥶 Very cold!"
        
        return f"{distance} {trend}"
    
    def update_stats_win(self, attempts, difficulty, score, game_time, guess_history, secret_number):
        """Update statistics for a win"""
        self.stats['games_played'] += 1
        self.stats['games_won'] += 1
        self.stats['total_attempts'] += attempts
        self.stats['win_streak'] += 1
        self.stats['total_score'] += score
        self.stats['difficulty_wins'][difficulty] += 1
        
        if self.stats['win_streak'] > self.stats['best_streak']:
            self.stats['best_streak'] = self.stats['win_streak']
        
        # Add to high scores
        self.add_high_score(score, attempts, difficulty, game_time)
        
        # Add to game history
        self.add_to_history(True, attempts, difficulty, score, game_time, guess_history, secret_number)
        
        # Check achievements
        self.check_achievements(attempts, difficulty)
        
        self.save_data()
    
    def update_stats_loss(self, attempts, difficulty, game_time, guess_history, secret_number):
        """Update statistics for a loss"""
        self.stats['games_played'] += 1
        self.stats['total_attempts'] += attempts
        self.stats['win_streak'] = 0
        
        # Add to game history
        self.add_to_history(False, attempts, difficulty, 0, game_time, guess_history, secret_number)
        
        self.save_data()
    
    def add_high_score(self, score, attempts, difficulty, game_time):
        """Add score to high scores list"""
        high_score = {
            'score': score,
            'attempts': attempts,
            'difficulty': difficulty,
            'time': game_time,
            'date': datetime.now().strftime('%Y-%m-%d %H:%M')
        }
        
        self.high_scores.append(high_score)
        self.high_scores.sort(key=lambda x: x['score'], reverse=True)
        self.high_scores = self.high_scores[:10]  # Keep top 10
    
    def add_to_history(self, won, attempts, difficulty, score, game_time, guess_history, secret_number):
        """Add game to history"""
        game_record = {
            'date': datetime.now().strftime('%Y-%m-%d %H:%M'),
            'won': won,
            'attempts': attempts,
            'difficulty': difficulty,
            'score': score,
            'time': game_time,
            'secret_number': secret_number,
            'guesses': guess_history
        }
        
        self.game_history.append(game_record)
        
        # Keep only last 100 games
        if len(self.game_history) > 100:
            self.game_history = self.game_history[-100:]
    
    def check_achievements(self, attempts, difficulty):
        """Check and unlock achievements"""
        new_achievements = []
        
        # First win
        if not self.achievements['first_win']['unlocked'] and self.stats['games_won'] == 1:
            self.achievements['first_win']['unlocked'] = True
            new_achievements.append('first_win')
        
        # Perfectionist (3 attempts or less)
        if not self.achievements['perfectionist']['unlocked'] and attempts <= 3:
            self.achievements['perfectionist']['unlocked'] = True
            new_achievements.append('perfectionist')
        
        # Persistent (10 games)
        if not self.achievements['persistent']['unlocked'] and self.stats['games_played'] >= 10:
            self.achievements['persistent']['unlocked'] = True
            new_achievements.append('persistent')
        
        # Lucky streak (3 wins in a row)
        if not self.achievements['lucky_streak']['unlocked'] and self.stats['win_streak'] >= 3:
            self.achievements['lucky_streak']['unlocked'] = True
            new_achievements.append('lucky_streak')
        
        # Expert player
        if not self.achievements['expert_player']['unlocked'] and difficulty == 'expert':
            self.achievements['expert_player']['unlocked'] = True
            new_achievements.append('expert_player')
        
        # Display new achievements
        for achievement in new_achievements:
            info = self.achievements[achievement]
            print(f"\\n🎖️ ACHIEVEMENT UNLOCKED: {info['name']}")
            print(f"   {info['desc']}")
    
    def calculate_score(self, attempts, max_attempts, difficulty, game_time):
        """Calculate game score"""
        base_score = 1000
        
        # Difficulty multiplier
        multipliers = {'easy': 1, 'medium': 1.5, 'hard': 2, 'expert': 3, 'custom': 1.2}
        difficulty_bonus = base_score * (multipliers.get(difficulty, 1) - 1)
        
        # Attempt bonus (more points for fewer attempts)
        attempt_bonus = (max_attempts - attempts) * 100
        
        # Time bonus (bonus for quick thinking, but not too harsh)
        time_bonus = max(0, 500 - int(game_time * 10))
        
        total_score = int(base_score + difficulty_bonus + attempt_bonus + time_bonus)
        return max(100, total_score)  # Minimum score of 100
    
    def show_statistics(self):
        """Display detailed statistics"""
        print("\\n📊 GAME STATISTICS")
        print("=" * 40)
        
        if self.stats['games_played'] == 0:
            print("No games played yet!")
            return
        
        print(f"Games played: {self.stats['games_played']}")
        print(f"Games won: {self.stats['games_won']}")
        
        win_rate = (self.stats['games_won'] / self.stats['games_played']) * 100
        print(f"Win rate: {win_rate:.1f}%")
        print(f"Current streak: {self.stats['win_streak']}")
        print(f"Best streak: {self.stats['best_streak']}")
        print(f"Total score: {self.stats['total_score']}")
        
        if self.stats['games_won'] > 0:
            avg_attempts = self.stats['total_attempts'] / self.stats['games_won']
            avg_score = self.stats['total_score'] / self.stats['games_won']
            print(f"Avg attempts/win: {avg_attempts:.1f}")
            print(f"Avg score/win: {avg_score:.0f}")
        
        print("\\nWins by difficulty:")
        for diff, wins in self.stats['difficulty_wins'].items():
            if wins > 0:
                print(f"  {diff.title()}: {wins}")
    
    def show_high_scores(self):
        """Display high scores"""
        print("\\n🏆 HIGH SCORES")
        print("=" * 50)
        
        if not self.high_scores:
            print("No high scores yet!")
            return
        
        for i, score in enumerate(self.high_scores, 1):
            print(f"{i:2d}. {score['score']:4d} pts | "
                  f"{score['attempts']} attempts | "
                  f"{score['difficulty'].title()} | "
                  f"{score['date']}")
    
    def show_achievements(self):
        """Display achievements"""
        print("\\n🎖️ ACHIEVEMENTS")
        print("=" * 40)
        
        unlocked_count = sum(1 for ach in self.achievements.values() if ach['unlocked'])
        total_count = len(self.achievements)
        print(f"Unlocked: {unlocked_count}/{total_count}")
        print()
        
        for key, ach in self.achievements.items():
            status = "✅" if ach['unlocked'] else "🔒"
            print(f"{status} {ach['name']}")
            print(f"   {ach['desc']}")
            print()
    
    def show_game_history(self):
        """Display recent game history"""
        print("\\n📈 GAME HISTORY (Last 10)")
        print("=" * 60)
        
        if not self.game_history:
            print("No games in history!")
            return
        
        recent_games = self.game_history[-10:]
        
        for game in reversed(recent_games):
            result = "WON" if game['won'] else "LOST"
            score_text = f"{game['score']} pts" if game['won'] else "0 pts"
            
            print(f"{game['date']} | {result:4s} | "
                  f"{game['attempts']} attempts | "
                  f"{game['difficulty'].title():6s} | "
                  f"{score_text}")
    
    def show_how_to_play(self):
        """Display game instructions"""
        print("\\n❓ HOW TO PLAY")
        print("=" * 40)
        print("1. Choose a difficulty level or create custom game")
        print("2. I'll think of a number within the chosen range")
        print("3. You guess the number")
        print("4. I'll tell you if your guess is too high or low")
        print("5. Keep guessing until you find the number or run out of attempts")
        print("\\nScoring:")
        print("• Base score varies by difficulty")
        print("• Bonus points for fewer attempts")
        print("• Time bonus for quick solving")
        print("• Unlock achievements for special accomplishments")
        print("\\nHints:")
        print("• 🔥 = Very close")
        print("• ♨️ = Close")
        print("• 🌡️ = Warm")
        print("• 🧊 = Cold")
        print("• 🎯 = Getting closer")
        print("• ❄️ = Getting further")
    
    def get_valid_guess(self, min_num, max_num, attempt_num):
        """Get valid guess with better formatting"""
        while True:
            try:
                guess = int(input(f"\\n[{attempt_num}] Your guess ({min_num}-{max_num}): "))
                
                if min_num <= guess <= max_num:
                    return guess
                else:
                    print(f"❌ Number must be between {min_num} and {max_num}!")
            
            except ValueError:
                print("❌ Please enter a valid number!")
    
    def run(self):
        """Main game loop"""
        print("Welcome to the Advanced Number Guessing Game! 🎯")
        
        while True:
            self.display_main_menu()
            
            choice = input("\\nEnter your choice (1-8): ").strip()
            
            if choice == '1':
                self.play_game_mode()
            elif choice == '2':
                self.show_statistics()
            elif choice == '3':
                self.show_high_scores()
            elif choice == '4':
                self.show_achievements()
            elif choice == '5':
                self.show_game_history()
            elif choice == '6':
                custom_settings = self.custom_game_setup()
                self.play_round('custom', custom_settings)
            elif choice == '7':
                self.show_how_to_play()
            elif choice == '8':
                print("\\n👋 Thanks for playing! See you next time!")
                self.save_data()
                break
            else:
                print("❌ Invalid choice! Please enter 1-8.")
            
            input("\\nPress Enter to continue...")

if __name__ == "__main__":
    game = AdvancedGuessingGame()
    game.run()
```

---

## 🎨 Phase 4: GUI Version (Optional)

### Implementation

```python
# gui_guessing_game.py

import tkinter as tk
from tkinter import ttk, messagebox
import random
import json
from datetime import datetime

class GUIGuessingGame:
    def __init__(self, root):
        self.root = root
        self.root.title("Number Guessing Game")
        self.root.geometry("500x600")
        self.root.resizable(False, False)
        
        # Game variables
        self.secret_number = None
        self.attempts = 0
        self.max_attempts = 10
        self.min_num = 1
        self.max_num = 100
        self.game_in_progress = False
        
        # Statistics
        self.stats = {'games_played': 0, 'games_won': 0, 'total_attempts': 0}
        self.load_stats()
        
        self.setup_ui()
        self.new_game()
    
    def setup_ui(self):
        """Set up the user interface"""
        # Main frame
        main_frame = ttk.Frame(self.root, padding="20")
        main_frame.grid(row=0, column=0, sticky=(tk.W, tk.E, tk.N, tk.S))
        
        # Title
        title_label = ttk.Label(
            main_frame, 
            text="🎯 Number Guessing Game", 
            font=('Arial', 18, 'bold')
        )
        title_label.grid(row=0, column=0, columnspan=2, pady=(0, 20))\n        
        # Game info frame
        info_frame = ttk.LabelFrame(main_frame, text="Game Info", padding="10")
        info_frame.grid(row=1, column=0, columnspan=2, sticky=(tk.W, tk.E), pady=(0, 10))
        
        self.range_label = ttk.Label(info_frame, text="Range: 1-100")
        self.range_label.grid(row=0, column=0, sticky=tk.W)
        
        self.attempts_label = ttk.Label(info_frame, text="Attempts: 0/10")
        self.attempts_label.grid(row=0, column=1, sticky=tk.E)
        
        # Difficulty selection
        diff_frame = ttk.LabelFrame(main_frame, text="Difficulty", padding="10")
        diff_frame.grid(row=2, column=0, columnspan=2, sticky=(tk.W, tk.E), pady=(0, 10))
        
        self.difficulty_var = tk.StringVar(value="medium")
        difficulties = [
            ("Easy (1-50, 15 attempts)", "easy"),
            ("Medium (1-100, 10 attempts)", "medium"),
            ("Hard (1-200, 8 attempts)", "hard")
        ]
        
        for i, (text, value) in enumerate(difficulties):
            rb = ttk.Radiobutton(
                diff_frame, 
                text=text, 
                variable=self.difficulty_var, 
                value=value,
                command=self.on_difficulty_change
            )
            rb.grid(row=i, column=0, sticky=tk.W)
        
        # Input frame
        input_frame = ttk.LabelFrame(main_frame, text="Your Guess", padding="10")
        input_frame.grid(row=3, column=0, columnspan=2, sticky=(tk.W, tk.E), pady=(0, 10))
        
        self.guess_var = tk.StringVar()
        self.guess_entry = ttk.Entry(
            input_frame, 
            textvariable=self.guess_var, 
            font=('Arial', 14),
            width=10,
            justify='center'
        )
        self.guess_entry.grid(row=0, column=0, padx=(0, 10))
        self.guess_entry.bind('<Return>', lambda e: self.make_guess())
        
        self.guess_button = ttk.Button(
            input_frame, 
            text="Guess!", 
            command=self.make_guess
        )
        self.guess_button.grid(row=0, column=1)
        
        # Feedback frame
        feedback_frame = ttk.LabelFrame(main_frame, text="Feedback", padding="10")
        feedback_frame.grid(row=4, column=0, columnspan=2, sticky=(tk.W, tk.E), pady=(0, 10))
        
        self.feedback_text = tk.Text(
            feedback_frame, 
            height=8, 
            width=50, 
            font=('Arial', 10),
            state='disabled',
            wrap=tk.WORD
        )
        self.feedback_text.grid(row=0, column=0, sticky=(tk.W, tk.E))
        
        # Scrollbar for feedback
        scrollbar = ttk.Scrollbar(feedback_frame, orient="vertical", command=self.feedback_text.yview)
        scrollbar.grid(row=0, column=1, sticky=(tk.N, tk.S))
        self.feedback_text.configure(yscrollcommand=scrollbar.set)
        
        # Control buttons
        button_frame = ttk.Frame(main_frame)
        button_frame.grid(row=5, column=0, columnspan=2, pady=(10, 0))\n        
        ttk.Button(button_frame, text="New Game", command=self.new_game).grid(row=0, column=0, padx=(0, 10))
        ttk.Button(button_frame, text="Statistics", command=self.show_stats).grid(row=0, column=1, padx=(0, 10))
        ttk.Button(button_frame, text="Hint", command=self.give_hint).grid(row=0, column=2)
        
        # Configure grid weights
        main_frame.columnconfigure(0, weight=1)
        main_frame.columnconfigure(1, weight=1)
        info_frame.columnconfigure(1, weight=1)
        feedback_frame.columnconfigure(0, weight=1)
    
    def load_stats(self):
        """Load statistics from file"""
        try:
            with open("gui_game_stats.json", "r") as f:
                self.stats = json.load(f)
        except FileNotFoundError:
            pass
    
    def save_stats(self):
        """Save statistics to file"""
        try:
            with open("gui_game_stats.json", "w") as f:
                json.dump(self.stats, f)
        except Exception as e:
            print(f"Could not save stats: {e}")
    
    def on_difficulty_change(self):
        """Handle difficulty change"""
        if not self.game_in_progress:
            self.new_game()
    
    def new_game(self):
        """Start a new game"""
        difficulty = self.difficulty_var.get()
        
        if difficulty == "easy":
            self.min_num, self.max_num = 1, 50
            self.max_attempts = 15
        elif difficulty == "medium":
            self.min_num, self.max_num = 1, 100
            self.max_attempts = 10
        elif difficulty == "hard":
            self.min_num, self.max_num = 1, 200
            self.max_attempts = 8
        
        self.secret_number = random.randint(self.min_num, self.max_num)
        self.attempts = 0
        self.game_in_progress = True
        
        # Update UI
        self.range_label.config(text=f"Range: {self.min_num}-{self.max_num}")
        self.attempts_label.config(text=f"Attempts: {self.attempts}/{self.max_attempts}")
        self.guess_var.set("")
        self.guess_entry.config(state='normal')
        self.guess_button.config(state='normal')
        
        # Clear and update feedback
        self.update_feedback("🎯 New game started! I'm thinking of a number between "
                           f"{self.min_num} and {self.max_num}.\\n"
                           f"You have {self.max_attempts} attempts. Good luck!\\n"
                           + "="*50 + "\\n")
    
    def update_feedback(self, message):
        """Update the feedback text area"""
        self.feedback_text.config(state='normal')
        self.feedback_text.insert(tk.END, message + "\\n")
        self.feedback_text.config(state='disabled')
        self.feedback_text.see(tk.END)
    
    def make_guess(self):
        """Process the player's guess"""
        if not self.game_in_progress:
            messagebox.showinfo("Game Over", "Please start a new game!")
            return
        
        try:
            guess = int(self.guess_var.get())
        except ValueError:
            messagebox.showerror("Invalid Input", "Please enter a valid number!")
            return
        
        if guess < self.min_num or guess > self.max_num:
            messagebox.showerror("Invalid Range", 
                               f"Please enter a number between {self.min_num} and {self.max_num}!")
            return
        
        self.attempts += 1
        self.attempts_label.config(text=f"Attempts: {self.attempts}/{self.max_attempts}")
        
        if guess == self.secret_number:
            # Player wins!
            self.update_feedback(f"🎉 CONGRATULATIONS! You guessed {self.secret_number} correctly!")
            self.update_feedback(f"It took you {self.attempts} attempts.")
            
            # Calculate score
            score = max(100, 1000 - (self.attempts - 1) * 100)
            self.update_feedback(f"Your score: {score} points")
            
            # Update statistics
            self.stats['games_played'] += 1
            self.stats['games_won'] += 1
            self.stats['total_attempts'] += self.attempts
            self.save_stats()
            
            self.end_game()
            
        elif self.attempts >= self.max_attempts:
            # Player loses
            self.update_feedback(f"💔 Game Over! You've used all {self.max_attempts} attempts.")
            self.update_feedback(f"The number was {self.secret_number}.")
            
            # Update statistics
            self.stats['games_played'] += 1
            self.stats['total_attempts'] += self.attempts
            self.save_stats()
            
            self.end_game()
            
        else:
            # Continue game
            if guess < self.secret_number:
                feedback = f"📈 {guess} is too low!"
            else:
                feedback = f"📉 {guess} is too high!"
            
            remaining = self.max_attempts - self.attempts
            feedback += f" {remaining} attempts remaining."
            
            # Add hint
            difference = abs(guess - self.secret_number)
            range_size = self.max_num - self.min_num
            
            if difference <= range_size * 0.1:
                feedback += " 🔥 You're very close!"
            elif difference <= range_size * 0.25:
                feedback += " ♨️ You're getting warm!"
            elif difference <= range_size * 0.5:
                feedback += " 🌡️ You're in the right area..."
            else:
                feedback += " 🧊 You're quite far off."
            
            self.update_feedback(feedback)
        
        self.guess_var.set("")
    
    def give_hint(self):
        """Provide a hint to the player"""
        if not self.game_in_progress:
            messagebox.showinfo("Game Over", "Please start a new game!")
            return
        
        # Generate range hint
        quarter = (self.max_num - self.min_num) // 4
        
        if self.secret_number <= self.min_num + quarter:
            hint = f"💡 Hint: The number is in the lower quarter ({self.min_num}-{self.min_num + quarter})"
        elif self.secret_number <= self.min_num + 2 * quarter:
            hint = f"💡 Hint: The number is in the lower half ({self.min_num}-{self.min_num + 2 * quarter})"
        elif self.secret_number <= self.min_num + 3 * quarter:
            hint = f"💡 Hint: The number is in the upper half ({self.min_num + 2 * quarter + 1}-{self.max_num})"
        else:
            hint = f"💡 Hint: The number is in the upper quarter ({self.min_num + 3 * quarter + 1}-{self.max_num})"
        
        self.update_feedback(hint)
    
    def end_game(self):
        """End the current game"""
        self.game_in_progress = False
        self.guess_entry.config(state='disabled')
        self.guess_button.config(state='disabled')
        self.update_feedback("\\nGame ended. Click 'New Game' to play again!")
    
    def show_stats(self):
        """Show game statistics"""
        if self.stats['games_played'] == 0:
            message = "No games played yet!"
        else:
            win_rate = (self.stats['games_won'] / self.stats['games_played']) * 100
            avg_attempts = self.stats['total_attempts'] / max(self.stats['games_won'], 1)
            
            message = f"""📊 Game Statistics
            
Games Played: {self.stats['games_played']}
Games Won: {self.stats['games_won']}
Win Rate: {win_rate:.1f}%
Average Attempts per Win: {avg_attempts:.1f}"""
        
        messagebox.showinfo("Statistics", message)

if __name__ == "__main__":
    root = tk.Tk()
    game = GUIGuessingGame(root)
    root.mainloop()
```

---

## 🧪 Testing Your Game

### Test Scenarios

1. **Basic Functionality**
   - Test winning on first guess
   - Test winning on last attempt
   - Test losing (using all attempts)
   - Test different difficulty levels

2. **Input Validation**
   - Enter non-numeric input
   - Enter numbers outside the range
   - Enter negative numbers
   - Enter decimal numbers

3. **Edge Cases**
   - Minimum and maximum numbers in range
   - Boundary values
   - Very large or small ranges (custom mode)

4. **Persistence Testing**
   - Play multiple games and check statistics
   - Close and reopen the program
   - Verify high scores are saved
   - Check achievement unlocking

---

## 🚀 Project Extensions

### Beginner Extensions
1. **Themed Versions**: Animals, colors, or movie guessing
2. **Multiplayer Mode**: Two players take turns guessing
3. **Sound Effects**: Add audio feedback for wins/losses
4. **Different Number Types**: Fractions, negative numbers

### Intermediate Extensions
1. **AI Opponent**: Computer tries to guess your number
2. **Tournament Mode**: Best of 5 games with scoring
3. **Category System**: Math facts, historical dates, etc.
4. **Mobile Version**: Convert to web app or mobile app

### Advanced Extensions
1. **Machine Learning**: AI learns your guessing patterns
2. **Network Multiplayer**: Play against remote players
3. **Adaptive Difficulty**: Game adjusts based on performance
4. **Voice Recognition**: Speak your guesses

---

## 🏆 Conclusion

Congratulations! You've built a complete number guessing game that demonstrates:

- **Game Logic**: Random generation and comparison algorithms
- **User Interface**: Both console and GUI versions
- **Data Management**: Statistics, high scores, and persistence
- **Error Handling**: Input validation and edge cases
- **Code Organization**: Classes, functions, and modularity

### Skills Practiced

✅ **Control Structures** (loops, conditionals)
✅ **Random Number Generation**
✅ **Input Validation**
✅ **File Operations**
✅ **Object-Oriented Programming**
✅ **GUI Programming**
✅ **Data Persistence**
✅ **Statistics and Analytics**
✅ **Achievement Systems**

**Excellent work!** 🎉 Ready for your next project? Try the [Password Generator](../PasswordGenerator/README.md) or explore other projects in the [Projects Directory](../README.md).