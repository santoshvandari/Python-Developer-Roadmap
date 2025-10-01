# Todo List Project

Build a task management application to organize and track your daily activities and projects.

## Project Overview

**What you'll build**: A todo list application that allows you to add, remove, mark as complete, and persist tasks across program runs.

**What you'll learn**:
- Working with lists and dictionaries
- File operations for data persistence
- Date and time handling
- User interface design
- Data validation and error handling

## Project Features

### Basic Features
- Add new tasks with descriptions
- Mark tasks as complete/incomplete
- Remove tasks from the list
- Display all tasks with status
- Save tasks to file for persistence

### Advanced Features
- Task categories and priorities
- Due dates and reminders
- Search and filter functionality
- Task statistics and progress tracking
- Export tasks to different formats

## Implementation Guide

### Phase 1: Basic Todo List
**Time**: 2-3 hours

Create a simple command-line todo list:
- Add tasks to a list
- Display tasks with numbering
- Mark tasks as done
- Remove tasks
- Basic menu system

**Key concepts**: Lists, dictionaries, loops, conditional statements

### Phase 2: Data Persistence
**Time**: 2-3 hours

Add file operations:
- Save tasks to JSON file
- Load tasks when program starts
- Handle file errors gracefully
- Backup functionality

**Key concepts**: File I/O, JSON handling, exception handling

### Phase 3: Enhanced Features
**Time**: 3-4 hours

Implement advanced functionality:
- Task priorities (high, medium, low)
- Due dates with date validation
- Task categories
- Search and filter options
- Progress statistics

**Key concepts**: Date/time operations, data filtering, validation

### Phase 4: GUI Version
**Time**: 4-5 hours

Create a graphical interface:
- Task list display with checkboxes
- Add/edit task dialogs
- Priority and category selection
- Progress visualization

**Key concepts**: GUI programming, event handling, data binding

## Getting Started

### Setup
1. Create project directory and files
2. Plan your data structure for tasks
3. Design the user interface flow

### Basic Task Structure
```python
task = {
    'id': 1,
    'description': 'Complete Python project',
    'completed': False,
    'created_date': '2025-10-01',
    'priority': 'high',
    'category': 'work'
}
```

### Core Functions
```python
def add_task(description, priority='medium', category='general'):
    # Add new task to list
    pass

def complete_task(task_id):
    # Mark task as completed
    pass

def remove_task(task_id):
    # Remove task from list
    pass

def display_tasks(filter_by=None):
    # Show tasks with optional filtering
    pass
```

## User Interface Design

### Command Line Menu
```
=== TODO LIST MANAGER ===
1. Add Task
2. View Tasks
3. Mark Complete
4. Remove Task
5. Search Tasks
6. Statistics
7. Exit

Choose an option: 
```

### Task Display Format
```
[1] [ ] High - Complete Python project (Work)
[2] [X] Medium - Buy groceries (Personal)
[3] [ ] Low - Read book chapter (Education)
```

## Data Management

### File Structure
- Use JSON format for easy reading/writing
- Include metadata (creation date, last modified)
- Implement backup system
- Handle concurrent access if needed

### Example JSON Structure
```json
{
  "tasks": [
    {
      "id": 1,
      "description": "Complete project",
      "completed": false,
      "created_date": "2025-10-01T10:00:00",
      "priority": "high",
      "category": "work",
      "due_date": "2025-10-15T23:59:59"
    }
  ],
  "metadata": {
    "last_modified": "2025-10-01T10:30:00",
    "total_tasks": 1,
    "completed_tasks": 0
  }
}
```

## Testing Your Application

### Test Scenarios
- Add multiple tasks with different properties
- Mark tasks as complete and incomplete
- Remove tasks and verify list updates
- Test file saving and loading
- Search for tasks with various criteria
- Test edge cases (empty list, invalid inputs)

### Data Validation
- Ensure task descriptions are not empty
- Validate date formats for due dates
- Check priority values are valid
- Handle duplicate task IDs

## Extensions and Improvements

### Beginner Extensions
- Task notes and detailed descriptions
- Simple reminder notifications
- Task completion time tracking
- Export to text or CSV format

### Intermediate Extensions
- Subtasks and task dependencies
- Recurring tasks
- Team collaboration features
- Integration with calendar applications

### Advanced Extensions
- Web-based interface
- Mobile app synchronization
- AI-powered task suggestions
- Integration with project management tools

## Common Issues and Solutions

**Issue**: File corruption or missing file
**Solution**: Implement backup system and file validation

**Issue**: Task IDs become inconsistent
**Solution**: Use UUID or implement proper ID management

**Issue**: Date parsing errors
**Solution**: Use datetime module with proper error handling

**Issue**: Large task lists become slow
**Solution**: Implement pagination and efficient data structures

## Learning Outcomes

After completing this project, you'll understand:
- How to design and implement data structures
- File operations and data persistence
- User input validation and error handling
- Date and time operations in Python
- Basic GUI programming concepts
- Software design patterns and organization

## File Structure

```
todo_list/
├── basic_todo.py          # Phase 1 implementation
├── persistent_todo.py     # Phase 2 with file operations
├── advanced_todo.py       # Phase 3 with full features
├── gui_todo.py           # Phase 4 GUI version
├── tasks.json            # Task data file
├── backup/               # Backup files directory
│   └── tasks_backup.json
└── README.md             # Project documentation
```

## Next Steps

Once you've completed your todo list:
1. Use it to manage your own tasks!
2. Add your favorite features and customizations
3. Share your implementation with others
4. Consider building a web version
5. Try the Contact Book project next for more data management practice

Excellent work on building a practical productivity tool!