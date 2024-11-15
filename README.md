# Go REST API with MySQL

This is a simple RESTful API built with Go and MySQL that provides CRUD operations for users and products.

## Prerequisites

1. Go installed on your system
2. MySQL server running
3. Create a database named `go-api-db`

## Setup

1. Create the database:
```sql
CREATE DATABASE go-api-db;
```

2. Update the database connection string in main.go if needed:
```go
db, err = sql.Open("mysql", "root:root@tcp(localhost:3306)/go-api-db")
```

3. Run the application:
```bash
go run main.go
```

## API Endpoints

### Users
- GET /users - Get all users
- GET /users/{id} - Get a specific user
- POST /users - Create a new user
- PUT /users/{id} - Update a user
- DELETE /users/{id} - Delete a user

### Products
- GET /products - Get all products
- GET /products/{id} - Get a specific product
- POST /products - Create a new product
- PUT /products/{id} - Update a product
- DELETE /products/{id} - Delete a product

## Example Requests

### Create User
```bash
curl -X POST http://localhost:8080/users -H "Content-Type: application/json" -d '{
    "name": "John Doe",
    "email": "john@example.com"
}'
```

### Create Product
```bash
curl -X POST http://localhost:8080/products -H "Content-Type: application/json" -d '{
    "name": "Sample Product",
    "price": 29.99,
    "description": "This is a sample product"
}'
```