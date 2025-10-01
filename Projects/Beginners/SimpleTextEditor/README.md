# Simple Text Editor Project

Build a basic text editor application with file operations and text manipulation features.

## Project Overview

**What you'll build**: A text editor that can open, edit, and save text files with basic formatting and search functionality.

**What you'll learn**:
- File input/output operations
- String manipulation and text processing
- Basic GUI programming with tkinter
- Event handling and user interface design
- Working with text widgets and menus

## Project Features

### Basic Features
- Open and display text files
- Edit text content
- Save files to disk
- Basic menu system (File, Edit)
- Text area with scrollbars

### Advanced Features
- Find and replace functionality
- Cut, copy, paste operations
- Undo/redo functionality
- Word count and statistics
- Basic text formatting
- Multiple file tabs

## Implementation Guide

### Phase 1: Basic File Operations
**Time**: 2-3 hours

Create command-line text editor:
- Read file contents
- Allow text editing
- Save changes back to file
- Handle file errors

**Key concepts**: File I/O, string operations, error handling

### Phase 2: GUI Interface
**Time**: 3-4 hours

Build graphical interface:
- Main window with text area
- File menu (New, Open, Save, Exit)
- Edit menu (Cut, Copy, Paste)
- Status bar

**Key concepts**: tkinter GUI, widgets, menu systems

### Phase 3: Enhanced Editing
**Time**: 3-4 hours

Add advanced features:
- Find and replace dialog
- Undo/redo functionality
- Line numbers display
- Word wrap toggle
- Font size and family selection

**Key concepts**: Advanced GUI programming, text processing

### Phase 4: Advanced Features
**Time**: 4-5 hours

Implement professional features:
- Syntax highlighting for code
- Multiple document interface
- Auto-save functionality
- Recent files menu
- Customizable themes

**Key concepts**: Advanced text processing, configuration management

## Getting Started

### Setup
1. Create project directory
2. Plan the user interface layout
3. Design the file handling system

### Basic Structure
```python
import tkinter as tk
from tkinter import filedialog, messagebox, scrolledtext

class SimpleTextEditor:
    def __init__(self, root):
        self.root = root
        self.current_file = None
        self.text_changed = False
        self.setup_ui()
    
    def setup_ui(self):
        # Create menu bar
        # Create text area
        # Create status bar
        pass
```

## User Interface Design

### Main Window Layout
- Menu bar at top (File, Edit, View, Help)
- Toolbar with common actions (optional)
- Large text editing area in center
- Status bar at bottom showing line/column, word count
- Scrollbars for text area

### Menu Structure
```
File
├── New (Ctrl+N)
├── Open (Ctrl+O)
├── Save (Ctrl+S)
├── Save As (Ctrl+Shift+S)
├── Recent Files
└── Exit

Edit
├── Undo (Ctrl+Z)
├── Redo (Ctrl+Y)
├── Cut (Ctrl+X)
├── Copy (Ctrl+C)
├── Paste (Ctrl+V)
├── Find (Ctrl+F)
└── Replace (Ctrl+H)
```

## Core Functionality

### File Operations
- New file: Clear text area and reset file path
- Open file: Use file dialog to select and load file
- Save file: Write current text to file
- Save As: Choose new location and save

### Text Editing
- Standard text input and editing
- Keyboard shortcuts for common operations
- Mouse support for selection and cursor positioning
- Clipboard integration

### Search and Replace
- Find text with highlighting
- Replace single or all occurrences
- Case-sensitive option
- Regular expression support (advanced)

## Implementation Examples

### Basic File Operations
```python
def open_file(self):
    file_path = filedialog.askopenfilename(
        title="Open File",
        filetypes=[("Text Files", "*.txt"), ("All Files", "*.*")]
    )
    if file_path:
        try:
            with open(file_path, 'r', encoding='utf-8') as file:
                content = file.read()
                self.text_area.delete(1.0, tk.END)
                self.text_area.insert(1.0, content)
                self.current_file = file_path
                self.update_title()
        except Exception as e:
            messagebox.showerror("Error", f"Could not open file: {e}")
```

### Text Change Detection
```python
def on_text_change(self, event=None):
    self.text_changed = True
    self.update_title()
    self.update_status_bar()

def update_title(self):
    title = "Simple Text Editor"
    if self.current_file:
        title += f" - {os.path.basename(self.current_file)}"
    if self.text_changed:
        title += " *"
    self.root.title(title)
```

## Testing Your Editor

### Test Scenarios
- Create new file and add content
- Open existing text files of various sizes
- Save files with different names and locations
- Test cut, copy, paste operations
- Search for text and replace content
- Test with special characters and Unicode

### Edge Cases
- Very large files (performance testing)
- Files with different encodings
- Read-only files
- Network file locations
- Invalid file paths

## Extensions and Improvements

### Beginner Extensions
- Word count display
- Simple spell checker
- Text statistics (characters, lines, paragraphs)
- Print functionality

### Intermediate Extensions
- Syntax highlighting for programming languages
- Auto-completion for common words
- Plugin system for extensions
- Customizable keyboard shortcuts

### Advanced Extensions
- Multiple document interface with tabs
- Project file management
- Integration with version control systems
- Collaborative editing features

## Common Issues and Solutions

**Issue**: Text encoding problems with special characters
**Solution**: Always specify UTF-8 encoding when reading/writing files

**Issue**: Large files cause application to freeze
**Solution**: Implement progressive loading and text streaming

**Issue**: Undo/redo not working properly
**Solution**: Use tkinter's built-in undo functionality or implement custom stack

**Issue**: Find/replace not finding all occurrences
**Solution**: Implement proper text search algorithms and handle edge cases

## Learning Outcomes

After completing this project, you'll understand:
- File I/O operations and error handling
- GUI programming with tkinter
- Event-driven programming concepts
- Text processing and manipulation
- User interface design principles
- Software architecture and organization

## File Structure

```
simple_text_editor/
├── basic_editor.py        # Phase 1 command-line version
├── gui_editor.py          # Phase 2 basic GUI
├── advanced_editor.py     # Phase 3 enhanced features
├── full_editor.py         # Phase 4 complete version
├── themes/                # Color themes and settings
│   └── default.json
├── icons/                 # UI icons (optional)
└── README.md              # Project documentation
```

## Next Steps

Once you've completed your text editor:
1. Use it to edit your other Python projects!
2. Add your favorite text editing features
3. Share your implementation and get feedback
4. Consider adding syntax highlighting for Python
5. Try the Contact Book project next for more GUI practice

Great job on building a practical productivity application!