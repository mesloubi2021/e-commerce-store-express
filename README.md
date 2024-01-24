# This is a Folked NodeJS server used for traning purpose. Contact Author if any.

This is an Express service that provides authorization functionality and includes separate folders for users and products.
It also uses Sequelize ORM with SQLite as the database, along with the JSON Web Token (JWT) and AJV libraries.

## Project Structure
 - `index.js`: The main entry point of the application.
 - `config.js`: Contains configuration files for the application.
 - `authorization`
   - `controllers`: Controller files for authentication endpoints.
   - `schemas`: JSON Schemas against which the body of various routes will be validated.
   - `routes.js`: Registers all the authentication routes.
 - `products`
   - `controllers`: Controller files for product master CRUD endpoints.
   - `schemas`: JSON Schemas against which the body of various routes will be validated.
   - `routes.js`: Registers all the product CRUD routes.
 - `users`
   - `controllers`: Controller files for user master CRUD endpoints.
   - `schemas`: JSON Schemas against which the body of various routes will be validated.
   - `routes.js`: Registers all the user CRUD routes.
 - `common`
   - `middlewares`: Various middlewares that can be used in various routes like (isAuthenticated, CheckPermissions etc.)
   - `models`: Sequelise models for the Product and User Tables
 - `storage`: Local storage, that stores all the SQLite tables.

## Prerequisites
Before running the application, make sure you have the following installed:
1. NodeJS (v18)
2. NPM (v9)

## Installation
1. Clone the repository: `git clone https://github.com/arvindkalra08/e-commerce`
2. Navigate to the project directory: `cd e-commerce-service`
3. Install the dependencies: `npm install`

## Usage

To start the service, run the following command:
```shell
npm start
```

## APIs

### SignUp
```
curl --location 'localhost:3000/signup' \
--data-raw '{
    "firstName": "Dinq",
    "lastName": "Truong",
    "email": "dinqtruong@gmail.com",
    "username": "dinqtruong",
    "password": "Qwertyuiop@!#$1091",
    "role": "admin",
    "age": 18
}'
```

### Login
```
curl --location 'localhost:3000/login' \
--data '{
    "username": "dinqtruong",
    "password": "Qwertyuiop@!#$1091"
}'
```

### Get Profile

```
curl --location 'localhost:3000/user' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjUsInVzZXJuYW1lIjoicXVhbmd0cnVvbmdkLWFkbWluIiwiaWF0IjoxNzA2MDY3NjEzLCJleHAiOjE3MDYwNzEyMTN9.UMs0wF5mSRH0skPDFfH_mREVQUgBxAhk4yroHmk8y28'
```

### Get Products

```
curl --location 'localhost:3000/product' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjUsInVzZXJuYW1lIjoicXVhbmd0cnVvbmdkLWFkbWluIiwiaWF0IjoxNzA2MDY3NjEzLCJleHAiOjE3MDYwNzEyMTN9.UMs0wF5mSRH0skPDFfH_mREVQUgBxAhk4yroHmk8y28'
```

## License
This project is licensed under the MIT License.

## Blog
https://blog.postman.com/how-to-create-a-rest-api-with-node-js-and-express/



