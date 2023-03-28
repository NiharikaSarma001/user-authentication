# User Authentication with FastAPI, OAuth2, and JWT
This is a sample project that demonstrates how to implement user authentication with FastAPI using OAuth2 and JSON Web Tokens (JWT).


# Features
-> User registration
-> User login/logout
-> Password hashing
-> JWT token generation and verification
-> Protected routes that require authentication

# Requirements
1. Python 3.7+
2. FastAPI
3. PyJWT
4. passlib

# Installation
1. Clone the repository
git clone https://github.com/NiharikaSarma001/user-authentication

2. Create a virtual environment: python -m venv env

3. Activate the virtual environment: source env/bin/activate (Unix) or env\Scripts\activate.bat (Windows).

4. Install the dependencies: pip install -r requirements.txt.

5. Start the server: uvicorn main:app --reload.
This will start the application on http://localhost:8000 .

# Endpoints
'/register'
This endpoint registers a new user in the system. It takes a JSON payload with the following fields:

username: the username of the new user.
password: the password of the new user.
email: the email address of the new user.
full_name: the full name of the new user.

POST /register HTTP/1.1
Content-Type: application/json

{
    "username": "niharika",
    "password": "password",
    "email": "abc@gmail.com",
    "full_name": "Niharika Sarma"
}

'/login'
This endpoint logs in an existing user and returns a JWT access token. It takes a form payload with the following fields:

username: the username of the existing user.
password: the password of the existing user.

POST /login HTTP/1.1
Content-Type: application/x-www-form-urlencoded

username=niharika&password=password

/token
This endpoint generates a new JWT access token. It takes no payload and requires the Authorization header with the Bearer scheme and the access token as the token value.

POST /token HTTP/1.1
Authorization: Bearer {access_token}

/users/me
This endpoint returns the details of the currently authenticated user. It takes no payload and requires the Authorization header with the Bearer scheme and the access token as the token value.

GET /users/me HTTP/1.1
Authorization: Bearer {access_token}

# Dependencies
FastAPI: a modern, fast (high-performance) web framework for building APIs with Python 3.7+.
Pydantic: data validation and settings management using Python type annotations.
passlib: a password hashing library for Python 2 & 3, which provides cross-platform implementations of over 30 password hashing algorithms.
JWT: a JSON Web Token implementation in Python.
uvicorn: a lightning-fast ASGI server implementation, using uvloop and httptools.
