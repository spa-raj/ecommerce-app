# Vibe Vault - E-commerce Application

## Overview

Welcome to Vibe Vault, a comprehensive e-commerce platform built with a modern microservices architecture. This repository serves as the central hub for the application, integrating the `product-service` and `user-service` to deliver a robust solution for managing products, categories, users, and authentication in an online retail environment.

![Ecommerce app architecture](https://github.com/sparsh3007/ecommerce-app/assets/49100336/05170673-7978-4438-bb0c-3993b3a988a1)

## Table of Contents
- [Features](#features)
  - [User Service](#user-service)
  - [Product Service](#product-service)
- [Architecture](#architecture)
- [Technology Stack](#technology-stack)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation & Setup](#installation--setup)
- [API Endpoints](#api-endpoints)
  - [User Service API](#user-service-api)
  - [Product Service API](#product-service-api)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Features

### [User Service](https://github.com/spa-raj/userservice)

The User Service handles all aspects of user management, authentication, and authorization.

![User Service diagram](https://github.com/sparsh3007/ecommerce-app/assets/49100336/8b04a0b7-b4a4-4938-b195-d50fbe5938c8)

-   **User Registration & Login**: Securely sign up new users and authenticate existing ones.
-   **Token-Based Authentication**: Utilizes JSON Web Tokens (JWT) for managing user sessions and securing endpoints.
-   **Role-Based Access Control (RBAC)**: Differentiates between user roles (e.g., `BUYER`, `SELLER`, `ADMIN`) to control access to various features.
-   **Admin Functionalities**: Provides endpoints for administrators to manage user roles.
-   **Logout**: Invalidate user sessions and tokens upon logout.

### [Product Service](https://github.com/spa-raj/productService)

The Product Service is responsible for managing the product catalog, including categories and inventory.

![Product Service Diagram](https://github.com/sparsh3007/ecommerce-app/assets/49100336/043cf617-7e3c-46de-8bdf-efba4373af0e)

-   **Product Management**: Full CRUD (Create, Read, Update, Delete) operations for products.
-   **Category Management**: Organize products into categories with full CRUD capabilities.
-   **Flexible Service Implementations**: Supports multiple data sources, including a local database and an external fake store API, which can be configured in the `application.properties` file.
-   **Product Search**: Enables users to search for products and filter them by category.

## Architecture

The application is built on a microservices architecture. Each service is a standalone Spring Boot application that communicates with others via RESTful APIs. This decoupled approach allows for independent development, deployment, and scaling of each service.

-   **User Service**: Manages all user-related data and authentication. [View Repository](https://github.com/spa-raj/userservice)
-   **Product Service**: Handles all product and category-related operations. [View Repository](https://github.com/spa-raj/productService)

## Technology Stack

-   **Java**: 17 & 21
-   **Framework**: Spring Boot
-   **Security**: Spring Security (JWT)
-   **ORM**: Hibernate
-   **Database**: MySQL
-   **Database Migration**: Flyway
-   **Build Tool**: Maven

## Getting Started

### Prerequisites

-   Java 17 or higher
-   Maven
-   MySQL

### Installation & Setup

1.  **Clone the repositories**:
    ```bash
    git clone [https://github.com/sparsh3007/ecommerce-app](https://github.com/sparsh3007/ecommerce-app)
    git clone [https://github.com/spa-raj/userservice](https://github.com/spa-raj/userservice)
    git clone [https://github.com/spa-raj/productService](https://github.com/spa-raj/productService)
    ```

2.  **Configure Databases**:
    -   Create two separate MySQL databases, one for the `userservice` and one for the `productservice`.
    -   Update the `application.properties` file in each service (`userservice/src/main/resources/application.properties` and `productservice/src/main/resources/application.properties`) with your MySQL database URL, username, and password.

3.  **Run Database Migrations**:
    Flyway will handle the database schema migrations automatically when the services are run.

4.  **Build the Services**:
    ```bash
    cd userservice
    mvn clean install
    cd ../productService
    mvn clean install
    ```

5.  **Run the Services**:
    Open two separate terminal windows to run the services concurrently.

    *Terminal 1 (User Service):*
    ```bash
    cd userservice
    mvn spring-boot:run
    ```

    *Terminal 2 (Product Service):*
    ```bash
    cd productService
    mvn spring-boot:run
    ```

## API Endpoints

### User Service API

-   `POST /auth/signup`: Register a new user.
-   `POST /auth/login`: Authenticate a user and receive a JWT.
-   `POST /auth/logout`: Invalidate a user's session.
-   `POST /auth/validate`: Validate a user's token.
-   `POST /roles/create`: Create a new user role (Admin only).
-   `GET /roles`: Retrieve all roles (Admin only).

### Product Service API

#### Category Management
-   `POST /categories`: Create a new category.
-   `GET /categories`: Retrieve all categories.
-   `GET /categories/id/{categoryId}`: Retrieve a category by its ID.
-   `GET /categories/name/{categoryName}`: Retrieve a category by its name.
-   `GET /categories/products/{category}`: Retrieve all products in a specific category.
-   `GET /categories/products`: Retrieve all products for a list of category IDs.

#### Product Management
-   `POST /products`: Add a new product (Requires SELLER or ADMIN role).
-   `GET /products`: Retrieve all products.
-   `GET /products/id/{productId}`: Retrieve a specific product by its ID.
-   `PUT /products/{productId}`: Update an existing product (Requires SELLER or ADMIN role).
-   `PATCH /products/{productId}`: Partially update an existing product (Requires SELLER or ADMIN role).
-   `DELETE /products/{productId}`: Delete a product by its ID (Requires SELLER or ADMIN role).

## Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

Please fork the repository and submit a pull request with your changes.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more information.

## Contact

Sparsh Raj - [sparsh.raj30@gmail.com](mailto:sparsh.raj30@gmail.com)

Project Link: [https://github.com/sparsh3007/ecommerce-app](https://github.com/sparsh3007/ecommerce-app)
