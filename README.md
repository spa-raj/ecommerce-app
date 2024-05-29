# E-commerce Application

## Overview

This repository serves as the main entry point for the E-commerce application. It integrates the `productService` and `userService` microservices to provide a complete solution for managing products and users in an online store.

## Features

### User Service

- **User Registration**: Allows new users to sign up. Checks if the user already exists.
- **User Login**: Validates user credentials and throws custom exceptions for invalid logins.
- **Authentication Service**: Manages authentication tokens and user sessions.

### Product Service

- **Product Management**: CRUD operations for managing product information.
- **Product Search**: Enables users to search for products by various criteria.
- **Inventory Management**: Keeps track of product stock and updates inventory accordingly.

## Architecture

The application follows a microservices architecture, with each service being a Spring Boot application. The services communicate with each other through RESTful APIs.

### Services

- **User Service**: Manages user data and authentication. [View Repository](https://github.com/sparsh3007/userservice)
- **Product Service**: Handles product-related operations. [View Repository](https://github.com/sparsh3007/productService)

### Technology Stack

- **Java**
- **Spring Boot**
- **Spring Security**
- **Hibernate**
- **MySQL**
- **Docker**

## Getting Started

### Prerequisites

- Java 11 or higher
- Maven
- Docker

### Installation

1. **Clone the repositories**:
    ```bash
    git clone https://github.com/sparsh3007/ecommerce-app
    git clone https://github.com/sparsh3007/userservice
    git clone https://github.com/sparsh3007/productService
    ```

2. **Build the Services**:
    ```bash
    cd userservice
    mvn clean install
    cd ../productService
    mvn clean install
    ```

3. **Run the Services**:
    ```bash
    cd userservice
    mvn spring-boot:run
    cd ../productService
    mvn spring-boot:run
    ```

### Docker

You can also run the services using Docker.

1. **Build Docker Images**:
    ```bash
    cd userservice
    docker build -t userservice:latest .
    cd ../productService
    docker build -t productservice:latest .
    ```

2. **Run Docker Containers**:
    ```bash
    docker run -d -p 8081:8081 userservice:latest
    docker run -d -p 8082:8082 productservice:latest
    ```

## API Endpoints

### User Service

- **POST /users/signup**: Register a new user.
- **POST /users/login**: Authenticate a user.

### Product Service

- **GET /products**: Retrieve all products.
- **GET /products/{id}**: Retrieve a specific product by ID.
- **POST /products**: Add a new product.
- **PUT /products/{id}**: Update an existing product.
- **DELETE /products/{id}**: Delete a product by ID.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License.

## Contact

If you have any questions or need further assistance, feel free to reach out at sparsh3007@gmail.com.
