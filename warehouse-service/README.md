# Warehouse Service

This README file provides an overview of the Warehouse Service, which is part of the Warehouse-Storefront microservices project. The Warehouse Service is responsible for managing warehouse operations, including inventory management and data storage.

## Table of Contents

- [Technologies Used](#technologies-used)
- [Setup Instructions](#setup-instructions)
- [Service Endpoints](#service-endpoints)
- [Running the Application](#running-the-application)
- [Testing](#testing)
- [Contributing](#contributing)

## Technologies Used

- Java 11
- Spring Boot
- Spring Data JPA
- RabbitMQ (for messaging)
- Maven
- H2 Database (for development)

## Setup Instructions

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/warehouse-storefront-microservices.git
   ```

2. Navigate to the warehouse-service directory:
   ```
   cd warehouse-storefront-microservices/warehouse-service
   ```

3. Build the project using Maven:
   ```
   mvn clean install
   ```

4. Configure the application properties in `src/main/resources/application.yml` as needed.

## Service Endpoints

The Warehouse Service exposes the following endpoints:

- `GET /api/warehouse/items` - Retrieve all items in the warehouse.
- `POST /api/warehouse/items` - Add a new item to the warehouse.
- `GET /api/warehouse/items/{id}` - Retrieve a specific item by ID.
- `PUT /api/warehouse/items/{id}` - Update an existing item.
- `DELETE /api/warehouse/items/{id}` - Delete an item from the warehouse.

## Running the Application

To run the Warehouse Service, execute the following command:

```
mvn spring-boot:run
```

The application will start on `http://localhost:8080`.

## Testing

Unit tests for the Warehouse Service can be found in the `src/test/java/com/example/warehouse` directory. To run the tests, use the following command:

```
mvn test
```

## Contributing

Contributions are welcome! Please submit a pull request or open an issue for any enhancements or bug fixes.

---

For more information about the overall project, please refer to the main README file located in the root directory of the repository.