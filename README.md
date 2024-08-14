# node-auth-app

REST API with Authentication (Node.js, Express, TypeScript, MongoDB)

This project implements a REST API for user authentication using Node.js, Express, TypeScript, and MongoDB. The code is based on a video guide by [Code With Antonio](https://www.codewithantonio.com/projects/rest-api). All rights and credit for the original guide belong to them.
Note that there are opportunities for improvement.

## Configuration

Replace the Mongo connection host and credentials with the MongoDB connection string you obtained from MongoDB Atlas or any other platform.

```bash
const MONGO_URL = '<mongo-connection-uri>'
```

## Installation

Run the following command in the project directory to install the required dependencies.

```bash
npm install
```

## Start the Application

Run the following command to launch the API server.

```bash
npm start
```

## Usage

```bash

# Register a New User

curl --location 'http://localhost:8080/auth/register' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "testEmail@gmail.com",
    "password": "testPassword1",
    "username": "testUser"
}'

```
```bash

# Login

# Replace <token> with the actual authentication token.
# Replace <userId> with the actual user ID.

curl --location 'http://localhost:8080/auth/login' \
--header 'Content-Type: application/json' \
--header 'Cookie: APP-AUTH=<token>' \
--data-raw '{
    "email": "testEmail@gmail.com",
    "password": "testPassword1"
}'

```
```bash

# Delete User

# Replace <token> with the actual authentication token.
# Replace <userId> with the actual user ID.

curl --location --request DELETE 'http://localhost:8080/users/<userId>' \
--header 'Cookie: APP-AUTH=<token>' \
--data ''

```
```bash

# Update User Details

# Replace <token> with the actual authentication token.
# Replace <userId> with the actual user ID.

curl --location --request PATCH 'http://localhost:8080/users/<userId>' \
--header 'Cookie: APP-AUTH=<token>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "username": "newUserName"
}'

```
```bash

# List Users

# Replace <token> with the actual authentication token.

curl --location 'http://localhost:8080/users' \
--header 'Cookie: APP-AUTH=<token>' \
--data ''

```
