# E-commerce Application

## Overview

This repository serves as the main entry point for the E-commerce application. It integrates the `productService` and `userService` microservices to provide a complete solution for managing products and users in an online store.

![Ecommerce app architecture](https://github.com/sparsh3007/ecommerce-app/assets/49100336/05170673-7978-4438-bb0c-3993b3a988a1)

## Features

### User Service

![User Service diagram](https://github.com/sparsh3007/ecommerce-app/assets/49100336/8b04a0b7-b4a4-4938-b195-d50fbe5938c8)


- **User Registration**: Allows new users to sign up. Checks if the user already exists.
- **User Login**: Validates user credentials and throws custom exceptions for invalid logins.
- **Authentication Service**: Manages authentication tokens and user sessions.

### Product Service

![Product Service Diagram](https://github.com/sparsh3007/ecommerce-app/assets/49100336/043cf617-7e3c-46de-8bdf-efba4373af0e)

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

## Getting Started

### Prerequisites

- Java 11 or higher
- Maven

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


## API Endpoints

### User Service

- **POST /users/signup**: Register a new user.
- **POST /users/login**: Authenticate a user.
- **POST /roles**: Create a new role
  
### Product Service

- **GET /products**: Retrieve all products.
- **GET /products/{id}**: Retrieve a specific product by ID.
- **POST /products**: Add a new product.
- **PUT /products/{id}**: Update an existing product.
- **DELETE /products/{id}**: Delete a product by ID.
- **GET /categories/{uuid}**: Retrieve a specific category by ID
- **GET /categories/products**: Retrieve all products for specific categories by category IDs
- **GET /categories/all**: Retreive all categories
- **GET /categories/products/{category}**: Retreive all products by category name

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License.

## Contact

If you have any questions or need further assistance, feel free to reach out at sparsh.raj30@gmail.com.
