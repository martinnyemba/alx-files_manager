# ALX Files Manager

## Overview

This project is a culmination of concepts learned throughout the back-end trimester at ALX, incorporating authentication, Node.js, MongoDB, Redis, pagination, and background processing. The objective is to build a simple platform for uploading and viewing files with additional functionalities like user authentication, permission handling, and image thumbnail generation.

**Author:** Martin Nyemba  
**Repository:** [alx-files_manager](https://github.com/martinnyemba/alx-files_manager)

---

## Features

- **User Authentication:** Secure access via token-based authentication.
- **File Management:**
  - Upload new files.
  - Change file permissions.
  - List and view files.
  - Generate image thumbnails.
- **Utilities:** Redis and MongoDB utilities for storage and caching.
- **API:** RESTful API endpoints for seamless interaction.

---

## Learning Objectives

By completing this project, you will be able to:
1. Create an API using Express.js.
2. Implement user authentication with tokens.
3. Utilize MongoDB for data storage.
4. Use Redis for temporary data storage and caching.
5. Set up and use background workers for processing tasks.

---

## Requirements

- **Environment:**
  - Ubuntu 18.04 LTS
  - Node.js (v12.x.x)
- **Editors:** `vi`, `vim`, `emacs`, `Visual Studio Code`
- **Coding Style:** ESLint compliant JavaScript (ES6)
- **Mandatory Files:**
  - `README.md` at the root of the project
  - Files must end with a new line
  - Use `.js` extension for all files
- **Setup:** Run `npm install` to install dependencies.

---

## Project Structure

```plaintext
alx-files_manager/
├── utils/
│   ├── redis.js          # Redis utility
│   └── db.js             # MongoDB utility
├── controllers/
│   ├── AppController.js  # Application status and statistics
│   ├── UsersController.js # User management
│   ├── AuthController.js # Authentication
│   └── FilesController.js # File management
├── routes/
│   └── index.js          # API route definitions
├── server.js             # Express server setup
├── package.json          # Project dependencies
└── .eslintrc.js          # ESLint configuration

```
---

Setup Instructions

1. Clone the repository:

git clone https://github.com/your-username/alx-files_manager.git
cd alx-files_manager


2. Install dependencies:

npm install


3. Configure environment variables:

DB_HOST: MongoDB host (default: localhost)

DB_PORT: MongoDB port (default: 27017)

DB_DATABASE: MongoDB database name (default: files_manager)

FOLDER_PATH: Path for storing files (default: /tmp/files_manager)



4. Start the server:

npm run start-server




---

API Endpoints

General

GET /status: Check the status of Redis and MongoDB.

GET /stats: Retrieve the count of users and files.


User Management

POST /users: Create a new user.

GET /users/me: Get the current authenticated user.


Authentication

GET /connect: Authenticate and get a token.

GET /disconnect: Sign out the current user.


File Management

POST /files: Upload a new file.

GET /files/:id: Retrieve a file's metadata or content.



---

Example Usage

Check Status

curl http://localhost:5000/status
# Output: { "redis": true, "db": true }

Create a User

curl -X POST http://localhost:5000/users \
-H "Content-Type: application/json" \
-d '{"email": "user@example.com", "password": "securepassword"}'
# Output: { "id": "<user-id>", "email": "user@example.com" }

Authenticate a User

curl http://localhost:5000/connect \
-H "Authorization: Basic <base64(email:password)>"
# Output: { "token": "<auth-token>" }

Upload a File

curl -X POST http://localhost:5000/files \
-H "X-Token: <auth-token>" \
-H "Content-Type: application/json" \
-d '{"name": "document.txt", "type": "file", "data": "<base64-encoded-data>"}'
# Output: { "id": "<file-id>", "name": "document.txt", ... }


---

Resources

Node.js Documentation

Express.js Guide

MongoDB Documentation

Redis Documentation

Mocha Documentation



---

License
ALX Africa
