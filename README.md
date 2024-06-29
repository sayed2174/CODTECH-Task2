# CODTECH-Task2



### Simple Authentication System with Token Management
# Overview
This project implements a basic authentication system with register and login functionality using Express.js. It uses bcrypt to hash passwords and JSON Web Tokens (JWT) for managing user sessions. The system includes endpoints for registering users, logging in, verifying tokens, and viewing stored data.

# Features
**User Registration:**Register a new user with a hashed password.

**User Login:** Authenticate a user and generate a JWT for session management.

**Token Management:** Store and verify JWTs for user sessions.

**User Data Storage:** Store user credentials and session tokens in memory.

**Static Files Serving:** Serve static files for the login interface.

Technologies Used
**Node.js:** JavaScript runtime environment.
**Express.js:** Web application framework for Node.js.
**bcrypt:** Library to hash passwords.
**jsonwebtoken (JWT):** Library to generate and verify tokens.
**body-parser:** Middleware to parse incoming request bodies.
**CORS:** Middleware to enable Cross-Origin Resource Sharing.
**HTML & CSS:** For serving static files.
# Prerequisites
**Node.js:** Ensure you have Node.js installed. You can download it from here.
**npm:** Node.js package manager, which comes with Node.js installation.
# Installation
**Clone the repository:**

# bash

**git clone https:**//github.com/yourusername/simple-auth-system.git
cd simple-auth-system
**Install dependencies:**

# bash
npm install
**Start the server:**

# bash
npm start
**Access the API:**
The API will be accessible at http://localhost:3000.

## Usage
# Register a New User
**Endpoint:** POST /register
**Body:**
{
  "username": "johndoe",
  "password": "mypassword"
}

**Response:**
{
  "message": "Registration successful"
}
# Login a User
**Endpoint:** POST /login
**Body:**
{
  "username": "johndoe",
  "password": "mypassword"
}
**Response:**
{
  "message":  "Login successful",
  "token":  "your_jwt_token"
}
## Retrieve All Registered Users
**Endpoint:** GET /database
**Response:**
[
  {
    "username":  "johndoe",
    "password":  "$2b$10$encryptedPassword"
  }
]
## Verify Token for User Authorization
**Endpoint:** GET /auth
**Response (if authorized):**
{
  "user":** "johndoe",
  "message":** "Authorized User Login"
}
**Response (if unauthorized):**
{
  "message":** "Unauthorized User Login"
}
## Retrieve All Session Tokens
**Endpoint:** GET /token
**Response:**
[
  {
    "token":  "your_jwt_token"
  }
]
## Detailed Endpoint Explanations
POST /register
Registers a new user by hashing their password and storing the credentials in memory.

**Request Body:**
{
  "username": "johndoe",
  "password": "mypassword"
}

**Response:**
{
  "message": "Registration successful"
}
POST /login
Authenticates a user by verifying their credentials and generates a JWT for the session.

**Request Body:**
{
  "username": "johndoe",
  "password": "mypassword"
}
**Response:**
{
  "message": "Login successful",
  "token": "your_jwt_token"
}
GET /database
Retrieves all registered users from the in-memory storage.

**Response:**
[
  {
    "username": "johndoe",
    "password": "$2b$10$encryptedPassword"
  }
]
GET /auth
Verifies the provided token to check if the user is authorized.

**Response (if authorized):**
{
  "user": "johndoe",
  "message": "Authorized User Login"
}
**Response (if unauthorized):**
{
  "message": "Unauthorized User Login"
}
GET /token
Retrieves all session tokens stored in memory.

**Response:**
[
  {
    "token":  "your_jwt_token"
  }
]
