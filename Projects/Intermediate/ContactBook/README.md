# Contact Book Project

Build a contact management system to store and organize personal and professional contacts.

## Project Overview

**What you'll build**: A contact book application that stores contact information, supports searching and filtering, and maintains data persistence.

**What you'll learn**:
- Object-oriented programming with classes
- Data validation and input sanitization
- File operations and data persistence
- Search and filtering algorithms
- Database basics (optional advanced feature)

## Project Features

### Core Features
- Add new contacts with multiple fields
- Edit existing contact information
- Delete contacts from the book
- Search contacts by name, phone, or email
- Display all contacts in organized format
- Save/load contacts to/from file

### Advanced Features
- Contact categories and groups
- Import/export contacts (CSV, JSON)
- Contact photos and additional fields
- Backup and restore functionality
- Advanced search with filters
- Contact statistics and analytics

## Implementation Guide

### Phase 1: Contact Class Design
**Time**: 2-3 hours

Create the Contact class and basic operations:
- Design Contact class with properties
- Add methods for contact manipulation
- Implement basic contact list management
- Create simple command-line interface

**Key concepts**: Classes, objects, methods, data encapsulation

### Phase 2: Data Persistence
**Time**: 2-3 hours

Add file operations:
- Save contacts to JSON file
- Load contacts on program start
- Handle file errors and corruption
- Implement backup system

**Key concepts**: File I/O, JSON serialization, error handling

### Phase 3: Search and Validation
**Time**: 3-4 hours

Enhance functionality:
- Input validation for email, phone numbers
- Advanced search capabilities
- Contact sorting options
- Data integrity checks

**Key concepts**: Regular expressions, data validation, search algorithms

### Phase 4: GUI and Advanced Features
**Time**: 4-5 hours

Build graphical interface:
- Contact list display with details
- Add/edit contact forms
- Search and filter interface
- Import/export functionality

**Key concepts**: GUI programming, data binding, file formats

## Getting Started

### Setup
1. Plan the contact data structure
2. Design the class hierarchy
3. Create the user interface flow

### Contact Class Design
```python
class Contact:
    def __init__(self, first_name, last_name, phone="", email="", address=""):
        self.first_name = first_name
        self.last_name = last_name
        self.phone = phone
        self.email = email
        self.address = address
        self.created_date = datetime.now()
        self.modified_date = datetime.now()
    
    def full_name(self):
        return f"{self.first_name} {self.last_name}"
    
    def validate_email(self):
        # Email validation logic
        pass
    
    def validate_phone(self):
        # Phone validation logic
        pass
```

### ContactBook Class
```python
class ContactBook:
    def __init__(self):
        self.contacts = []
        self.filename = "contacts.json"
        self.load_contacts()
    
    def add_contact(self, contact):
        # Add contact to list
        pass
    
    def search_contacts(self, query):
        # Search functionality
        pass
    
    def save_contacts(self):
        # Save to file
        pass
```

## Data Structure Design

### Contact Information Fields
- **Required**: First name, last name
- **Optional**: Phone number, email address, physical address
- **Metadata**: Creation date, last modified date
- **Advanced**: Birthday, company, job title, notes, categories

### Data Validation Rules
- Name fields: Non-empty, reasonable length
- Email: Valid email format using regex
- Phone: Valid phone number format
- Address: Optional but structured if provided

### File Storage Format
```json
{
  "contacts": [
    {
      "first_name": "John",
      "last_name": "Doe",
      "phone": "+1-555-123-4567",
      "email": "john.doe@example.com",
      "address": "123 Main St, City, State 12345",
      "created_date": "2025-10-01T10:00:00",
      "modified_date": "2025-10-01T10:00:00",
      "categories": ["work", "friend"]
    }
  ],
  "metadata": {
    "version": "1.0",
    "total_contacts": 1,
    "last_backup": "2025-10-01T09:00:00"
  }
}
```

## User Interface Design

### Command Line Interface
```
=== CONTACT BOOK ===
1. Add Contact
2. View All Contacts
3. Search Contacts
4. Edit Contact
5. Delete Contact
6. Export Contacts
7. Import Contacts
8. Exit

Choose an option: 
```

### Contact Display Format
```
[1] John Doe
    Phone: +1-555-123-4567
    Email: john.doe@example.com
    Address: 123 Main St, City, State 12345
    Categories: work, friend
    Added: 2025-10-01
```

## Core Functionality Implementation

### Search Features
- Search by name (partial matches)
- Search by phone number
- Search by email address
- Filter by categories
- Advanced search with multiple criteria

### Data Validation Examples
```python
import re

def validate_email(email):
    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return re.match(pattern, email) is not None

def validate_phone(phone):
    # Remove non-digit characters for validation
    digits = re.sub(r'\D', '', phone)
    return len(digits) >= 10
```

### Import/Export Features
- Export to CSV for spreadsheet compatibility
- Export to JSON for backup/restore
- Import from various formats
- Data mapping and conversion

## Testing Your Contact Book

### Test Scenarios
- Add contacts with various field combinations
- Test search functionality with different queries
- Validate email and phone number formats
- Test file save/load operations
- Import/export with sample data
- Handle edge cases (empty fields, special characters)

### Data Integrity Tests
- Duplicate contact detection
- Data corruption recovery
- Large contact list performance
- Concurrent access handling

## Extensions and Improvements

### Beginner Extensions
- Contact photos and avatars
- Birthday reminders
- Contact notes and comments
- Simple contact sharing

### Intermediate Extensions
- Database storage (SQLite)
- Contact synchronization with phone/email
- Advanced contact analytics
- Contact relationship mapping

### Advanced Extensions
- Cloud synchronization
- Multi-user support with permissions
- Integration with email clients
- API for external applications

## Common Issues and Solutions

**Issue**: Contact data becomes corrupted
**Solution**: Implement data validation and automatic backups

**Issue**: Search becomes slow with many contacts
**Solution**: Implement indexing and optimized search algorithms

**Issue**: Import fails with different file formats
**Solution**: Add robust file format detection and conversion

**Issue**: Duplicate contacts created
**Solution**: Implement duplicate detection based on multiple fields

## Learning Outcomes

After completing this project, you'll understand:
- Object-oriented programming principles
- Data validation and sanitization techniques
- File operations and data serialization
- Search and filtering algorithms
- User interface design patterns
- Error handling and data integrity

## File Structure

```
contact_book/
├── models/
│   ├── contact.py         # Contact class definition
│   └── contact_book.py    # ContactBook class
├── utils/
│   ├── validation.py      # Data validation functions
│   └── file_handler.py    # File I/O operations
├── ui/
│   ├── cli_interface.py   # Command-line interface
│   └── gui_interface.py   # Graphical interface (optional)
├── data/
│   ├── contacts.json      # Main contact data
│   └── backups/           # Backup files
├── tests/
│   └── test_contacts.py   # Unit tests
└── README.md              # Project documentation
```

## Next Steps

Once you've completed your contact book:
1. Add your real contacts and use it daily
2. Implement your most-wanted features
3. Share with friends and get feedback
4. Consider mobile app version
5. Try the Expense Tracker project next for more data management

Excellent work on building a practical data management application!