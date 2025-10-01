# Quiz Game Project

Build an interactive quiz application with multiple question types, scoring, and progress tracking.

## Project Overview

**What you'll build**: A quiz game that loads questions from files, presents them to users, tracks scores, and provides feedback on performance.

**What you'll learn**:
- Object-oriented programming with classes
- JSON file handling for data storage
- Game logic and state management
- User interface design and interaction
- Score calculation and statistics
- Randomization and question shuffling

## Project Features

### Core Features
- Load questions from JSON files
- Multiple choice and true/false questions
- Score tracking and calculation
- Timer functionality (optional)
- Results summary and feedback
- Save high scores

### Advanced Features
- Multiple quiz categories
- Difficulty levels
- Question randomization
- Detailed statistics and analytics
- User profiles and progress tracking
- Export results and certificates

## Implementation Guide

### Phase 1: Basic Quiz Structure
**Time**: 2-3 hours

Create core quiz functionality:
- Question and Quiz classes
- Basic question presentation
- Score calculation
- Simple command-line interface

**Key concepts**: Classes, methods, basic game logic

### Phase 2: Data Management
**Time**: 2-3 hours

Add file operations:
- Load questions from JSON files
- Save and load user scores
- Handle different question types
- Error handling for file operations

**Key concepts**: File I/O, JSON handling, data validation

### Phase 3: Enhanced Features
**Time**: 3-4 hours

Implement advanced functionality:
- Categories and difficulty levels
- Timer and time tracking
- Question randomization
- Detailed feedback and explanations

**Key concepts**: Advanced data structures, timing, randomization

### Phase 4: GUI and Polish
**Time**: 4-5 hours

Create graphical interface:
- Question display with buttons
- Progress bars and timers
- Results visualization
- Settings and preferences

**Key concepts**: GUI programming, visual design, user experience

## Getting Started

### Setup
1. Plan the question data structure
2. Design the class hierarchy
3. Create sample question files

### Question Class Design
```python
class Question:
    def __init__(self, text, options, correct_answer, explanation="", difficulty="medium"):
        self.text = text
        self.options = options  # List of possible answers
        self.correct_answer = correct_answer  # Index or text of correct answer
        self.explanation = explanation
        self.difficulty = difficulty
        self.category = ""
    
    def is_correct(self, user_answer):
        return user_answer == self.correct_answer
    
    def get_points(self):
        difficulty_points = {"easy": 1, "medium": 2, "hard": 3}
        return difficulty_points.get(self.difficulty, 1)
```

### Quiz Class Design
```python
import random
import time
from datetime import datetime

class Quiz:
    def __init__(self, questions, title="General Quiz"):
        self.questions = questions
        self.title = title
        self.current_question = 0
        self.score = 0
        self.start_time = None
        self.user_answers = []
        self.time_limit = None  # seconds per question
    
    def start(self):
        self.start_time = datetime.now()
        self.shuffle_questions()
    
    def shuffle_questions(self):
        random.shuffle(self.questions)
    
    def get_current_question(self):
        if self.current_question < len(self.questions):
            return self.questions[self.current_question]
        return None
    
    def submit_answer(self, answer):
        question = self.get_current_question()
        if question:
            is_correct = question.is_correct(answer)
            if is_correct:
                self.score += question.get_points()
            
            self.user_answers.append({
                'question': question.text,
                'user_answer': answer,
                'correct_answer': question.correct_answer,
                'is_correct': is_correct
            })
            
            self.current_question += 1
            return is_correct
        return False
```

## Question Data Structure

### JSON Format
```json
{
  "quiz_title": "Python Programming Quiz",
  "category": "Programming",
  "questions": [
    {
      "id": 1,
      "text": "What is the output of print(2 ** 3)?",
      "type": "multiple_choice",
      "options": ["6", "8", "9", "12"],
      "correct_answer": 1,
      "explanation": "2 ** 3 means 2 to the power of 3, which equals 8.",
      "difficulty": "easy",
      "points": 1
    },
    {
      "id": 2,
      "text": "Python is a compiled language.",
      "type": "true_false",
      "options": ["True", "False"],
      "correct_answer": 1,
      "explanation": "Python is an interpreted language, not compiled.",
      "difficulty": "medium",
      "points": 2
    }
  ]
}
```

### Question Types
- **Multiple Choice**: 4 options, one correct
- **True/False**: Two options
- **Fill in the Blank**: Text input required
- **Matching**: Match items from two lists

## User Interface Design

### Command Line Interface
```plaintext
=== PYTHON PROGRAMMING QUIZ ===

Question 1 of 10                    Score: 0

What is the output of print(2 ** 3)?

A) 6
B) 8
C) 9
D) 12

Your answer (A/B/C/D): B

Correct! 2 ** 3 means 2 to the power of 3, which equals 8.

Press Enter to continue...
```

### GUI Layout
- Question counter and progress bar
- Question text display area
- Answer options as buttons or radio buttons
- Next/Submit button
- Score display
- Timer (if enabled)

## Game Logic Implementation

### Quiz Flow
```python
class QuizGame:
    def __init__(self):
        self.quizzes = {}
        self.high_scores = []
        self.load_quizzes()
        self.load_scores()
    
    def load_quizzes(self):
        # Load quiz files from data directory
        import os
        import json
        
        quiz_dir = "data/quizzes"
        for filename in os.listdir(quiz_dir):
            if filename.endswith('.json'):
                with open(os.path.join(quiz_dir, filename), 'r') as f:
                    quiz_data = json.load(f)
                    self.quizzes[quiz_data['category']] = self.create_quiz(quiz_data)
    
    def create_quiz(self, quiz_data):
        questions = []
        for q_data in quiz_data['questions']:
            question = Question(
                text=q_data['text'],
                options=q_data['options'],
                correct_answer=q_data['correct_answer'],
                explanation=q_data.get('explanation', ''),
                difficulty=q_data.get('difficulty', 'medium')
            )
            questions.append(question)
        
        return Quiz(questions, quiz_data['quiz_title'])
```

### Scoring System
```python
class ScoreCalculator:
    @staticmethod
    def calculate_final_score(quiz):
        total_possible = sum(q.get_points() for q in quiz.questions)
        percentage = (quiz.score / total_possible) * 100 if total_possible > 0 else 0
        
        return {
            'raw_score': quiz.score,
            'total_possible': total_possible,
            'percentage': percentage,
            'grade': ScoreCalculator.get_letter_grade(percentage),
            'time_taken': ScoreCalculator.calculate_time_taken(quiz)
        }
    
    @staticmethod
    def get_letter_grade(percentage):
        if percentage >= 90: return 'A'
        elif percentage >= 80: return 'B'
        elif percentage >= 70: return 'C'
        elif percentage >= 60: return 'D'
        else: return 'F'
```

## Advanced Features

### Timer Implementation
```python
import threading
import time

class QuizTimer:
    def __init__(self, time_limit, callback):
        self.time_limit = time_limit
        self.callback = callback
        self.start_time = None
        self.is_running = False
    
    def start(self):
        self.start_time = time.time()
        self.is_running = True
        timer_thread = threading.Thread(target=self._run_timer)
        timer_thread.start()
    
    def _run_timer(self):
        while self.is_running and self.get_remaining_time() > 0:
            time.sleep(0.1)
        
        if self.is_running:
            self.callback()  # Time's up!
    
    def get_remaining_time(self):
        if not self.start_time:
            return self.time_limit
        elapsed = time.time() - self.start_time
        return max(0, self.time_limit - elapsed)
```

### Statistics and Analytics
```python
class QuizStatistics:
    def __init__(self, quiz_results):
        self.results = quiz_results
    
    def get_category_performance(self):
        # Analyze performance by question category
        pass
    
    def get_difficulty_analysis(self):
        # Show performance by difficulty level
        pass
    
    def get_improvement_suggestions(self):
        # Provide personalized feedback
        pass
```

## Testing Your Quiz Game

### Test Scenarios
- Load different quiz files
- Answer questions correctly and incorrectly
- Test timer functionality
- Verify score calculations
- Test with various question types
- Handle invalid inputs gracefully

### Sample Test Data
```json
{
  "quiz_title": "Test Quiz",
  "category": "Test",
  "questions": [
    {
      "text": "Test question?",
      "type": "multiple_choice",
      "options": ["A", "B", "C", "D"],
      "correct_answer": 0,
      "difficulty": "easy"
    }
  ]
}
```

## Extensions and Improvements

### Beginner Extensions
- Hint system for difficult questions
- Achievement badges and rewards
- Question favorites and bookmarks
- Simple quiz creation tool

### Intermediate Extensions
- Multiplayer quiz competitions
- Adaptive difficulty adjustment
- Integration with external quiz APIs
- Mobile app version

### Advanced Extensions
- AI-powered question generation
- Speech recognition for answers
- Virtual reality quiz environments
- Learning management system integration

## Common Issues and Solutions

**Issue**: Questions not loading from files
**Solution**: Check file paths, JSON syntax, and error handling

**Issue**: Timer not working correctly
**Solution**: Use proper threading and time management

**Issue**: Scores not calculating properly
**Solution**: Debug scoring logic and validate question data

**Issue**: GUI freezing during quiz
**Solution**: Use proper event handling and avoid blocking operations

## Learning Outcomes

After completing this project, you'll understand:
- Object-oriented programming design patterns
- File operations and data serialization
- Game logic and state management
- User interface design and interaction
- Threading and timing operations
- Data analysis and statistics

## File Structure

```
quiz_game/
├── models/
│   ├── question.py        # Question class
│   ├── quiz.py           # Quiz class
│   └── game.py           # Main game logic
├── data/
│   ├── quizzes/          # Quiz JSON files
│   │   ├── python.json
│   │   ├── history.json
│   │   └── science.json
│   └── scores.json       # High scores
├── ui/
│   ├── cli_interface.py  # Command-line interface
│   └── gui_interface.py  # Graphical interface
├── utils/
│   ├── timer.py          # Timer functionality
│   ├── statistics.py     # Analytics and stats
│   └── file_handler.py   # File operations
└── README.md             # Project documentation
```

## Next Steps

Once you've completed your quiz game:
1. Create quiz content for your favorite subjects
2. Challenge friends and family to play
3. Add your own creative features
4. Share quizzes with the community
5. Try the Server project next for web-based applications

Excellent work on building an engaging educational tool!