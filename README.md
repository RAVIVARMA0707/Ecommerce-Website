# E-Commerce Website🛒🛒

## Overview

This project is a full-stack e-commerce website using React for the frontend, Spring Boot for the backend, and MySQL as the database. The application allows users to browse products, add them to the cart, and make purchases. Admins can manage the product inventory through CRUD operations.

## Features🪶

- Product listing and details
- Shopping cart functionality
- Order management
- Admin panel for product management
- Responsive design
- Add, update, delete, and create products with images

## Technologies Used 💻

### Frontend 🤖

- React
- Redux
- Axios
- React Router

### Backend

- Spring Boot
- Spring Data JPA
- MySQL

## Prerequisites

- Node.js and npm
- Java 8 or higher
- Maven 3.6 or higher
- MySQL

## Setup Instructions

### Frontend

1. **Navigate to the frontend directory:**
    ```bash
    cd frontend
    ```

2. **Install dependencies:**
    ```bash
    npm install
    ```

3. **Run the frontend server:**
    ```bash
    npm start
    ```

    The frontend will start running at `http://localhost:3000`.

### Backend

1. **Navigate to the backend directory:**
    ```bash
    cd backend
    ```

2. **Configure the MySQL Database:**

    Create a database in MySQL:

    ```sql
    CREATE DATABASE ecommerce;
    ```

    Update the `application.properties` file located in `src/main/resources` with your MySQL database configuration:

    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/ecommerce
    spring.datasource.username=your-username
    spring.datasource.password=your-password
    spring.jpa.hibernate.ddl-auto=update
    ```

3. **Build and Run the Backend:**
    ```bash
    mvn clean install
    mvn spring-boot:run
    ```

    The backend will start running at `http://localhost:8080`.

## API Endpoints

### Products

- **Get All Products:**
  - **URL:** `/api/products`
  - **Method:** `GET`

- **Get Product by ID:**
  - **URL:** `/api/product/{id}`
  - **Method:** `GET`

- **Add a Product:**
  - **URL:** `/api/product`
  - **Method:** `POST`
  - **Request Body:**
    ```json
    {
        "name": "Product Name",
        "description": "Product Description",
        "brand": "Brand",
        "price": 100.0,
        "category": "Category",
        "releaseDate": "2023-07-01",
        "productAvailable": true,
        "stockQuantity": 50,
        "imageName": "image.jpg",
        "imageType": "image/jpeg",
        "imageData": "<image byte data>"
    }
    ```

- **Update a Product:**
  - **URL:** `/api/product/{prodId}`
  - **Method:** `PUT`
  - **Request Body:**
    ```json
    {
        "name": "Updated Product Name",
        "description": "Updated Product Description",
        "brand": "Updated Brand",
        "price": 150.0,
        "category": "Updated Category",
        "releaseDate": "2023-07-01",
        "productAvailable": true,
        "stockQuantity": 60,
        "imageName": "updated_image.jpg",
        "imageType": "image/jpeg",
        "imageData": "<updated image byte data>"
    }
    ```

- **Delete a Product:**
  - **URL:** `/api/product/{prodId}`
  - **Method:** `DELETE`

- **Search Products:**
  - **URL:** `/api/products/search`
  - **Method:** `GET`
  - **Request Params:** `keyword`

## Project Structure

### Backend
```bash
backend
├── src
│ ├── main
│ │ ├── java
│ │ │ └── com
│ │ │ └── ravi
│ │ │ └── ecom_proj
│ │ │ ├── controller
│ │ │ │ └── ProductController.java
│ │ │ ├── model
│ │ │ │ └── Product.java
│ │ │ ├── repository
│ │ │ │ └── ProductRepository.java
│ │ │ ├── service
│ │ │ │ └── ProductService.java
│ │ │ └── EcommerceApplication.java
│ ├── resources
│ │ ├── application.properties
│ │ └── schema.sql
│ └── test
│ └── java
│ └── com
│ └── ravi
│ └── ecom_proj
│ └── EcommerceApplicationTests.java
├── pom.xml
└── ...
```

