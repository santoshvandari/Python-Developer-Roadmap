# Web Server Project

Build a web server application with API endpoints, database integration, and user authentication.

## Project Overview

**What you'll build**: A complete web server that handles HTTP requests, serves web pages, manages data with a database, and provides API endpoints.

**What you'll learn**:
- Web frameworks (Flask/FastAPI)
- HTTP protocols and RESTful APIs
- Database operations and ORM
- User authentication and sessions
- Template rendering and static files
- Deployment and production considerations

## Project Features

### Core Features
- HTTP request handling (GET, POST, PUT, DELETE)
- Serve static files (HTML, CSS, JavaScript)
- Template rendering with dynamic content
- Basic routing and URL handling
- JSON API endpoints
- Error handling and logging

### Advanced Features
- User registration and authentication
- Database integration with SQLite/PostgreSQL
- Session management and cookies
- File upload handling
- API rate limiting and security
- Real-time features with WebSockets

## Implementation Guide

### Phase 1: Basic Web Server
**Time**: 3-4 hours

Create a simple HTTP server:
- Basic Flask application setup
- Handle GET and POST requests
- Serve static files
- Simple HTML templates

**Key concepts**: HTTP protocol, web frameworks, routing

### Phase 2: Database Integration
**Time**: 4-5 hours

Add data persistence:
- Database setup (SQLite)
- Create data models
- CRUD operations
- Database migrations

**Key concepts**: Databases, ORM, data modeling

### Phase 3: User Authentication
**Time**: 4-5 hours

Implement user system:
- User registration and login
- Password hashing
- Session management
- Protected routes

**Key concepts**: Authentication, security, session management

### Phase 4: API and Frontend
**Time**: 5-6 hours

Build complete application:
- RESTful API endpoints
- Frontend with JavaScript
- AJAX requests
- API documentation

**Key concepts**: REST APIs, frontend integration, documentation

## Getting Started

### Required Libraries
```bash
pip install flask flask-sqlalchemy flask-login werkzeug requests
```

### Basic Flask Setup
```python
from flask import Flask, render_template, request, jsonify
from flask_sqlalchemy import SQLAlchemy
from datetime import datetime

app = Flask(__name__)
app.config['SECRET_KEY'] = 'your-secret-key-here'
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///app.db'
db = SQLAlchemy(app)

@app.route('/')
def home():
    return render_template('index.html')

if __name__ == '__main__':
    app.run(debug=True)
```

## Database Models

### User Model
```python
from flask_sqlalchemy import SQLAlchemy
from werkzeug.security import generate_password_hash, check_password_hash
from datetime import datetime

class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String(80), unique=True, nullable=False)
    email = db.Column(db.String(120), unique=True, nullable=False)
    password_hash = db.Column(db.String(120), nullable=False)
    created_at = db.Column(db.DateTime, default=datetime.utcnow)
    
    def set_password(self, password):
        self.password_hash = generate_password_hash(password)
    
    def check_password(self, password):
        return check_password_hash(self.password_hash, password)
```

### Content Model
```python
class Post(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    title = db.Column(db.String(100), nullable=False)
    content = db.Column(db.Text, nullable=False)
    author_id = db.Column(db.Integer, db.ForeignKey('user.id'), nullable=False)
    created_at = db.Column(db.DateTime, default=datetime.utcnow)
    updated_at = db.Column(db.DateTime, default=datetime.utcnow)
    
    author = db.relationship('User', backref=db.backref('posts', lazy=True))
```

## API Endpoints

### RESTful API Design
```python
# Users API
@app.route('/api/users', methods=['GET'])
def get_users():
    users = User.query.all()
    return jsonify([{
        'id': user.id,
        'username': user.username,
        'email': user.email
    } for user in users])

@app.route('/api/users', methods=['POST'])
def create_user():
    data = request.get_json()
    
    if not data or not data.get('username') or not data.get('email'):
        return jsonify({'error': 'Missing required fields'}), 400
    
    user = User(
        username=data['username'],
        email=data['email']
    )
    user.set_password(data['password'])
    
    db.session.add(user)
    db.session.commit()
    
    return jsonify({'message': 'User created successfully'}), 201

# Posts API
@app.route('/api/posts', methods=['GET'])
def get_posts():
    posts = Post.query.all()
    return jsonify([{
        'id': post.id,
        'title': post.title,
        'content': post.content,
        'author': post.author.username,
        'created_at': post.created_at.isoformat()
    } for post in posts])

@app.route('/api/posts/<int:post_id>', methods=['GET'])
def get_post(post_id):
    post = Post.query.get_or_404(post_id)
    return jsonify({
        'id': post.id,
        'title': post.title,
        'content': post.content,
        'author': post.author.username,
        'created_at': post.created_at.isoformat()
    })
```

## Authentication System

### User Registration
```python
from flask import session, redirect, url_for, flash

@app.route('/register', methods=['GET', 'POST'])
def register():
    if request.method == 'POST':
        username = request.form['username']
        email = request.form['email']
        password = request.form['password']
        
        # Validation
        if User.query.filter_by(username=username).first():
            flash('Username already exists')
            return redirect(url_for('register'))
        
        user = User(username=username, email=email)
        user.set_password(password)
        
        db.session.add(user)
        db.session.commit()
        
        flash('Registration successful')
        return redirect(url_for('login'))
    
    return render_template('register.html')

@app.route('/login', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        username = request.form['username']
        password = request.form['password']
        
        user = User.query.filter_by(username=username).first()
        
        if user and user.check_password(password):
            session['user_id'] = user.id
            return redirect(url_for('dashboard'))
        else:
            flash('Invalid username or password')
    
    return render_template('login.html')
```

## Frontend Templates

### Base Template (base.html)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{% block title %}My Web App{% endblock %}</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <div class="container">
            <a class="navbar-brand" href="{{ url_for('home') }}">My App</a>
            <div class="navbar-nav ms-auto">
                {% if 'user_id' in session %}
                    <a class="nav-link" href="{{ url_for('dashboard') }}">Dashboard</a>
                    <a class="nav-link" href="{{ url_for('logout') }}">Logout</a>
                {% else %}
                    <a class="nav-link" href="{{ url_for('login') }}">Login</a>
                    <a class="nav-link" href="{{ url_for('register') }}">Register</a>
                {% endif %}
            </div>
        </div>
    </nav>
    
    <div class="container mt-4">
        {% with messages = get_flashed_messages() %}
            {% if messages %}
                {% for message in messages %}
                    <div class="alert alert-info">{{ message }}</div>
                {% endfor %}
            {% endif %}
        {% endwith %}
        
        {% block content %}{% endblock %}
    </div>
    
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

### Home Page (index.html)
```html
{% extends "base.html" %}

{% block title %}Home - My Web App{% endblock %}

{% block content %}
<div class="row">
    <div class="col-md-8">
        <h1>Welcome to My Web App</h1>
        <p class="lead">This is a full-featured web application built with Flask.</p>
        
        <h2>Recent Posts</h2>
        <div id="posts-container">
            <!-- Posts will be loaded here via JavaScript -->
        </div>
    </div>
    
    <div class="col-md-4">
        <div class="card">
            <div class="card-body">
                <h5 class="card-title">Quick Stats</h5>
                <p>Total Users: <span id="user-count">-</span></p>
                <p>Total Posts: <span id="post-count">-</span></p>
            </div>
        </div>
    </div>
</div>

<script>
// Load posts via AJAX
fetch('/api/posts')
    .then(response => response.json())
    .then(posts => {
        const container = document.getElementById('posts-container');
        posts.forEach(post => {
            const postElement = document.createElement('div');
            postElement.className = 'card mb-3';
            postElement.innerHTML = `
                <div class="card-body">
                    <h5 class="card-title">${post.title}</h5>
                    <p class="card-text">${post.content.substring(0, 100)}...</p>
                    <small class="text-muted">By ${post.author} on ${new Date(post.created_at).toLocaleDateString()}</small>
                </div>
            `;
            container.appendChild(postElement);
        });
        
        document.getElementById('post-count').textContent = posts.length;
    });
</script>
{% endblock %}
```

## Security Considerations

### Input Validation
```python
from flask import request
import re

def validate_email(email):
    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return re.match(pattern, email) is not None

def validate_input(data, required_fields):
    errors = []
    for field in required_fields:
        if field not in data or not data[field].strip():
            errors.append(f'{field} is required')
    return errors
```

### Rate Limiting
```python
from flask_limiter import Limiter
from flask_limiter.util import get_remote_address

limiter = Limiter(
    app,
    key_func=get_remote_address,
    default_limits=["200 per day", "50 per hour"]
)

@app.route('/api/posts', methods=['POST'])
@limiter.limit("10 per minute")
def create_post():
    # Post creation logic
    pass
```

## Testing Your Server

### Manual Testing
- Test all routes with different HTTP methods
- Verify authentication and authorization
- Test API endpoints with various data
- Check error handling and edge cases

### Automated Testing
```python
import unittest
from app import app, db

class ServerTestCase(unittest.TestCase):
    def setUp(self):
        app.config['TESTING'] = True
        app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///:memory:'
        self.app = app.test_client()
        
        with app.app_context():
            db.create_all()
    
    def test_home_page(self):
        response = self.app.get('/')
        self.assertEqual(response.status_code, 200)
    
    def test_api_posts(self):
        response = self.app.get('/api/posts')
        self.assertEqual(response.status_code, 200)
        self.assertEqual(response.content_type, 'application/json')
```

## Deployment

### Production Setup
```python
# config.py
import os

class Config:
    SECRET_KEY = os.environ.get('SECRET_KEY') or 'dev-secret-key'
    SQLALCHEMY_DATABASE_URI = os.environ.get('DATABASE_URL') or 'sqlite:///app.db'
    SQLALCHEMY_TRACK_MODIFICATIONS = False

class ProductionConfig(Config):
    DEBUG = False
    SQLALCHEMY_DATABASE_URI = os.environ.get('DATABASE_URL')

class DevelopmentConfig(Config):
    DEBUG = True
```

### Using Gunicorn
```bash
# Install Gunicorn
pip install gunicorn

# Run production server
gunicorn -w 4 -b 0.0.0.0:8000 app:app
```

## Extensions and Improvements

### Beginner Extensions
- Add contact form and email sending
- Implement basic search functionality
- Add pagination for posts
- Create admin dashboard

### Intermediate Extensions
- Add real-time chat with WebSockets
- Implement caching with Redis
- Add file upload and image processing
- Create mobile API with proper versioning

### Advanced Extensions
- Microservices architecture
- Container deployment with Docker
- API gateway and load balancing
- Advanced monitoring and logging

## Learning Outcomes

After completing this project, you'll understand:
- Web development fundamentals
- HTTP protocol and RESTful API design
- Database design and operations
- User authentication and security
- Frontend-backend integration
- Deployment and production considerations

## File Structure

```
web_server/
├── app.py                 # Main application file
├── config.py             # Configuration settings
├── models.py             # Database models
├── routes/
│   ├── auth.py           # Authentication routes
│   ├── api.py            # API endpoints
│   └── main.py           # Main page routes
├── templates/
│   ├── base.html         # Base template
│   ├── index.html        # Home page
│   ├── login.html        # Login form
│   └── register.html     # Registration form
├── static/
│   ├── css/
│   ├── js/
│   └── images/
├── tests/
│   └── test_app.py       # Unit tests
├── requirements.txt      # Dependencies
└── README.md             # Project documentation
```

## Next Steps

Once you've completed your web server:
1. Deploy it to a cloud platform (Heroku, AWS, DigitalOcean)
2. Add your own creative features and functionality
3. Learn about microservices and scaling
4. Explore modern frameworks like FastAPI or Django
5. Try the Data Analysis Dashboard project for visualization skills

Excellent work on building a complete web application!