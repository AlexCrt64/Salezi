# Strapi Project - Seller Management

## Overview

This project is built with [Strapi](https://strapi.io/), a headless CMS, to manage sellers and their associated data. The project exposes APIs to handle CRUD operations for sellers while running on port **1337**.

---

## Setup Instructions

### Prerequisites

- [Node.js](https://nodejs.org/) (18.x or 20.x recommended)

### Installation Steps

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/AlexCrt64/Salezi
   cd Salezi
   ```

### Install Node.js Dependencies

```bash
npm install
```

### Setup Environment
Create a .env file in the project root with the following content:

APP_KEYS=FqGKi9qE5F6g1pjYIbpdNg==,0zjBwsPXJAi7EGQPLGwETA==,s1RVa8bjBfgNTZh+UCdKfA==,gXDzXMk0b8jsiqsWrWhP4Q==
API_TOKEN_SALT=zTq/ILY+p+DhZeVQcclxoA==
ADMIN_JWT_SECRET=B+Wz5cxPtecO3hy6voAWFw==
TRANSFER_TOKEN_SALT=PMZv/pggxt19evPJK9Km7g==

### Start the Server
Run in development mode:

```bash
npm run develop
```
Access the Strapi admin panel at http://localhost:1337/admin.

### Seller Routes

## Base URL
All requests should be made to http://localhost:1337/api.


# Available Endpoints

1. GET Sellers
URL: /sellers
Method: GET
Description: Retrieve all sellers.
Response Example:
```json
[
  {
    "id": 1,
    "Name": "John Doe",
    "email": "johndoe@example.com"
  }
]
```


2. GET Seller by ID
URL: /sellers/:id
Method: GET
Description: Retrieve a single seller by their ID.


3. POST Create a Seller
URL: /sellers
Method: POST
Authentication: Requires a Bearer token.
Body Example:
```json
{
  "data": {
    "Name": "Jane Doe",
    "email": "janedoe@example.com",
    "Password": "securepassword"
  }
}
```


4. PUT Update a Seller
URL: /sellers/:id
Method: PUT
Authentication: Requires a Bearer token.
Body Example:
```json
{
  "data": {
    "Name": "Updated Name",
    "email": "updatedemail@example.com",
    "Password": "updatedpassword"
  }
}
```


5. DELETE Seller by ID
URL: /sellers/:id
Method: DELETE
Authentication: Requires a Bearer token.


# Authentication

To interact with protected endpoints, obtain a Bearer token by sending a POST request to:
URL: /auth/local

Body Example:
```json
{
  "identifier": "your_email@example.com",
  "password": "your_password"
}
```
Response Example:
```json
{
  "jwt": "your_bearer_token"
}
```
Include this token in the Authorization header for protected routes:

```makefile
Authorization: Bearer <your_token>
```


This README includes instructions for setting up Strapi, explains seller-specific routes, and highlights how to authenticate API requests.