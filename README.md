# Flask Authentication App

A simple Flask web application with user registration, login, and dashboard functionality using SQLAlchemy database and bcrypt password hashing.

## Features

- **User Registration**: Create new user accounts with validation
  - Name validation (non-empty)
  - Email validation (non-empty, unique)
  - Password validation (minimum 6 characters)
  - Duplicate email prevention

- **User Login**: Authenticate users with email and password
  - Secure password verification using bcrypt
  - Session management

- **Dashboard**: Protected user dashboard accessible after login
  - Display user information
  - Accessible only to authenticated users

- **Logout**: Securely logout users and clear session

## Project Structure

```
FlaskAUTHapp/
├── app.py                 # Main application file with routes and database models
├── activate.bat          # Virtual environment activation script
├── instance/             # Database instance folder
├── __pycache__/          # Python cache files
└── templates/            # HTML templates
    ├── base.html         # Base template
    ├── index.html        # Home page
    ├── register.html     # Registration page
    ├── login.html        # Login page
    └── dashboard.html    # User dashboard
```

## Requirements

- Python 3.7+
- Flask
- Flask-SQLAlchemy
- bcrypt

## Installation

1. Clone the repository
2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   venv\Scripts\activate  # On Windows
   ```

3. Install dependencies:
   ```bash
   pip install flask flask-sqlalchemy bcrypt
   ```

4. Run the application:
   ```bash
   python app.py
   ```

The application will be available at `http://localhost:5000`

## Usage

### Register a New User
1. Navigate to `/register`
2. Enter your full name, email, and password (minimum 6 characters)
3. Click "Register"
4. You'll be redirected to the login page

### Login
1. Navigate to `/login`
2. Enter your registered email and password
3. Click "Login"
4. You'll be redirected to your dashboard

### Dashboard
1. View your profile information
2. Click "Logout" to end your session

## Validation Rules

The application enforces server-side validation for:
- **Name**: Must not be empty
- **Email**: Must not be empty and must be unique
- **Password**: Must not be empty and must be at least 6 characters long

Error messages are displayed if validation fails.

## Security Features

- **Password Hashing**: Passwords are hashed using bcrypt before storage
- **Session Management**: User sessions are managed securely
- **SQL Database**: SQLite database for persistent data storage

## Database

The application uses SQLite database to store user information:
- User ID (Primary Key)
- Name
- Email (Unique)
- Hashed Password

## Routes

- `/` - Home page
- `/register` - User registration page
- `/login` - User login page
- `/dashboard` - User dashboard (requires authentication)
- `/logout` - Logout user

## License

This project is open source and available under the MIT License.
