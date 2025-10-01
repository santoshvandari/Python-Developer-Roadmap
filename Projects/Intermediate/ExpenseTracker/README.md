# Expense Tracker Project

Build a personal finance management tool to track income, expenses, and analyze spending patterns.

## Project Overview

**What you'll build**: An expense tracking application that records financial transactions, categorizes spending, and provides insights into your financial habits.

**What you'll learn**:
- Working with dates and time data
- Data analysis and visualization
- File operations and data persistence
- Mathematical calculations and statistics
- Creating reports and summaries

## Project Features

### Core Features
- Add income and expense transactions
- Categorize transactions (food, transport, entertainment, etc.)
- View transaction history
- Calculate totals and balances
- Generate monthly/yearly reports
- Data persistence across sessions

### Advanced Features
- Budget planning and tracking
- Spending analysis with charts
- Recurring transaction support
- Export data to various formats
- Multi-currency support
- Financial goal tracking

## Implementation Guide

### Phase 1: Basic Transaction Management
**Time**: 2-3 hours

Create core transaction functionality:
- Transaction class design
- Add/view transactions
- Basic categorization
- Simple calculations

**Key concepts**: Classes, date handling, basic math operations

### Phase 2: Data Analysis
**Time**: 3-4 hours

Add analysis features:
- Monthly/yearly summaries
- Category-wise breakdown
- Balance calculations
- Trend analysis

**Key concepts**: Data aggregation, statistical calculations, date operations

### Phase 3: Reporting and Visualization
**Time**: 3-4 hours

Implement reporting:
- Generate detailed reports
- Create simple charts and graphs
- Export functionality
- Budget vs actual comparisons

**Key concepts**: Data visualization, file export, report generation

### Phase 4: Advanced Features
**Time**: 4-5 hours

Add sophisticated functionality:
- Budget planning interface
- Recurring transactions
- Advanced filtering and search
- Goal tracking and notifications

**Key concepts**: Advanced data structures, scheduling, notification systems

## Getting Started

### Setup
1. Plan the transaction data structure
2. Design category system
3. Create the user interface flow

### Transaction Class Design
```python
from datetime import datetime
from enum import Enum

class TransactionType(Enum):
    INCOME = "income"
    EXPENSE = "expense"

class Transaction:
    def __init__(self, amount, category, description, transaction_type, date=None):
        self.amount = float(amount)
        self.category = category
        self.description = description
        self.type = transaction_type
        self.date = date or datetime.now()
        self.id = self.generate_id()
    
    def generate_id(self):
        # Generate unique transaction ID
        pass
```

### ExpenseTracker Class
```python
class ExpenseTracker:
    def __init__(self):
        self.transactions = []
        self.categories = {
            'expense': ['Food', 'Transport', 'Entertainment', 'Utilities', 'Other'],
            'income': ['Salary', 'Freelance', 'Investment', 'Gift', 'Other']
        }
        self.load_data()
    
    def add_transaction(self, amount, category, description, transaction_type):
        # Add new transaction
        pass
    
    def get_balance(self):
        # Calculate current balance
        pass
    
    def get_monthly_summary(self, month, year):
        # Generate monthly report
        pass
```

## Data Structure Design

### Transaction Data
```json
{
  "id": "txn_20251001_001",
  "amount": 25.50,
  "category": "Food",
  "description": "Lunch at restaurant",
  "type": "expense",
  "date": "2025-10-01T12:30:00",
  "tags": ["restaurant", "lunch"],
  "payment_method": "credit_card"
}
```

### Category Structure
```python
CATEGORIES = {
    'expense': {
        'Food': ['Groceries', 'Restaurants', 'Takeout'],
        'Transport': ['Gas', 'Public Transport', 'Taxi'],
        'Entertainment': ['Movies', 'Games', 'Subscriptions'],
        'Bills': ['Rent', 'Utilities', 'Internet'],
        'Shopping': ['Clothing', 'Electronics', 'Household']
    },
    'income': {
        'Work': ['Salary', 'Bonus', 'Overtime'],
        'Business': ['Sales', 'Services', 'Freelance'],
        'Investment': ['Dividends', 'Interest', 'Capital Gains'],
        'Other': ['Gift', 'Refund', 'Miscellaneous']
    }
}
```

## User Interface Design

### Main Menu
```plaintext
=== EXPENSE TRACKER ===
1. Add Transaction
2. View Transactions
3. Monthly Summary
4. Category Analysis
5. Balance Report
6. Budget Manager
7. Export Data
8. Exit

Current Balance: $1,250.75
Choose an option: 
```

### Transaction Entry Form
```plaintext
=== ADD TRANSACTION ===
Type (1-Income, 2-Expense): 2
Amount: $25.50
Category: Food
Description: Lunch at restaurant
Date (YYYY-MM-DD) or Enter for today: 2025-10-01

Transaction added successfully!
```

## Core Features Implementation

### Balance Calculation
```python
def calculate_balance(self):
    total_income = sum(t.amount for t in self.transactions 
                      if t.type == TransactionType.INCOME)
    total_expenses = sum(t.amount for t in self.transactions 
                        if t.type == TransactionType.EXPENSE)
    return total_income - total_expenses
```

### Monthly Summary
```python
def get_monthly_summary(self, month, year):
    monthly_transactions = [
        t for t in self.transactions 
        if t.date.month == month and t.date.year == year
    ]
    
    income = sum(t.amount for t in monthly_transactions 
                if t.type == TransactionType.INCOME)
    expenses = sum(t.amount for t in monthly_transactions 
                  if t.type == TransactionType.EXPENSE)
    
    return {
        'month': f"{month}/{year}",
        'income': income,
        'expenses': expenses,
        'net': income - expenses,
        'transaction_count': len(monthly_transactions)
    }
```

### Category Analysis
```python
def analyze_spending_by_category(self, start_date=None, end_date=None):
    filtered_transactions = self.filter_by_date(start_date, end_date)
    expenses = [t for t in filtered_transactions 
               if t.type == TransactionType.EXPENSE]
    
    category_totals = {}
    for transaction in expenses:
        category = transaction.category
        category_totals[category] = category_totals.get(category, 0) + transaction.amount
    
    return category_totals
```

## Reporting Features

### Monthly Report Format
```plaintext
=== MONTHLY REPORT - October 2025 ===

Income:
  Salary:     $3,000.00
  Freelance:    $500.00
  Total:      $3,500.00

Expenses:
  Food:         $450.00
  Transport:    $200.00
  Bills:        $800.00
  Other:        $150.00
  Total:      $1,600.00

Net Income:   $1,900.00
Transactions: 45
```

### Data Export Options
- CSV format for spreadsheet analysis
- JSON format for backup/restore
- PDF reports for sharing
- Simple text summaries

## Testing Your Expense Tracker

### Test Scenarios
- Add various types of transactions
- Test date calculations and filtering
- Verify balance calculations
- Generate reports for different time periods
- Test data persistence and loading
- Handle edge cases (negative amounts, future dates)

### Sample Test Data
```python
test_transactions = [
    Transaction(3000, "Salary", "Monthly salary", TransactionType.INCOME),
    Transaction(25, "Food", "Lunch", TransactionType.EXPENSE),
    Transaction(50, "Transport", "Gas", TransactionType.EXPENSE),
    Transaction(100, "Entertainment", "Movie tickets", TransactionType.EXPENSE)
]
```

## Extensions and Improvements

### Beginner Extensions
- Receipt photo attachment
- Simple budgeting alerts
- Currency conversion
- Transaction search functionality

### Intermediate Extensions
- Investment tracking
- Bill reminder system
- Advanced data visualization
- Mobile app synchronization

### Advanced Extensions
- Machine learning for expense prediction
- Bank account integration
- Multi-user family budgeting
- Financial planning tools

## Common Issues and Solutions

**Issue**: Date calculations are incorrect
**Solution**: Use datetime module properly and handle timezones

**Issue**: Floating point precision errors with money
**Solution**: Use decimal module for precise financial calculations

**Issue**: Reports are slow with many transactions
**Solution**: Implement efficient data filtering and caching

**Issue**: Data loss during program crashes
**Solution**: Implement auto-save and backup mechanisms

## Learning Outcomes

After completing this project, you'll understand:
- Date and time manipulation in Python
- Data analysis and aggregation techniques
- Financial calculations and precision handling
- Report generation and data visualization
- File operations and data persistence
- User interface design for data entry

## File Structure

```
expense_tracker/
├── models/
│   ├── transaction.py     # Transaction class
│   └── expense_tracker.py # Main tracker class
├── utils/
│   ├── date_utils.py      # Date manipulation helpers
│   ├── calculations.py    # Financial calculations
│   └── export_utils.py    # Data export functions
├── reports/
│   ├── monthly_report.py  # Monthly report generator
│   └── category_report.py # Category analysis
├── data/
│   ├── transactions.json  # Transaction data
│   ├── categories.json    # Category definitions
│   └── backups/           # Backup files
├── ui/
│   ├── cli_interface.py   # Command-line interface
│   └── gui_interface.py   # Graphical interface (optional)
└── README.md              # Project documentation
```

## Next Steps

Once you've completed your expense tracker:
1. Start tracking your real expenses!
2. Analyze your spending patterns
3. Set up budgets and financial goals
4. Share insights with family or friends
5. Try the Web Scraper project next for data collection skills

Fantastic work on building a practical financial management tool!