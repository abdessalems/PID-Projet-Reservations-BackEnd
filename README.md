
# PID – Projet Réservations (Back-End)

## Project Overview

**PID – Projet Réservations** is the back-end system for a theater reservation application, built using **Java Spring Boot** with a microservice architecture. The back-end manages user authentication, show reservations, catalog management, and role-based access control. The system communicates via RESTful APIs and uses **MySQL** as its database for data persistence.

### Key Features

- **User Management**: User registration, login, profile updates, and role-based access (Admin, Producer, Critic, Member).
- **Reservation System**: Manage show reservations, including seat selection and user-specific booking history.
- **Show Catalog Management**: CRUD operations for shows, synchronized with external APIs, and supporting CSV import/export.
- **Review System**: Allow members and critics to post reviews on shows.
- **Admin Back-Office**: Secure admin interface for managing users, shows, and reservations.

---

## Microservice Architecture

The back-end is divided into distinct microservices, each handling a specific aspect of the system:

1. **User Service**: Manages user data (registration, login, profile updates) and authentication via **JWT**.
2. **Reservation Service**: Manages reservations, including booking, listing, and cancellation.
3. **Catalog Service**: Handles CRUD operations for shows and syncs show data with external APIs.
4. **Review Service**: Allows users to submit and manage reviews for shows.
5. **Admin Service**: Provides admin functionalities for managing users, shows, and reservations.

---

## Technologies Used

- **Java 17**: Core programming language.
- **Spring Boot**: Framework for developing RESTful APIs.
- **Spring Cloud**: Manages microservice discovery and communication.
- **Spring Data JPA**: Interacts with the **MySQL** database for data persistence.
- **MySQL**: Relational database for storing users, reservations, and show details.
- **Spring Security**: Ensures role-based access control and API security using **JWT**.
- **Eureka**: Service discovery tool for registering and locating microservices.
- **Zuul** or **Spring Cloud Gateway**: API gateway for routing external requests to internal microservices.
- **Docker**: Used for containerization and deployment of microservices.

---

## Database Configuration

**MySQL** is used to persist user, show, and reservation data. You can configure the database connection in the `application.properties` file for each microservice.

```properties
# MySQL Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/reservation_system
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
```

Database tables include:

- **Users**: Stores user credentials and roles.
- **Shows**: Stores show details (title, date, venue, etc.).
- **Reservations**: Links users to their show reservations.
- **Reviews**: Stores reviews submitted by users.

---

## Running the Application

### Prerequisites:
- **Java 17+**
- **Maven** (for building the project)
- **MySQL** (for database)
- **Docker** (optional, for containerization)

### Steps:

1. **Clone the Repository**:
  
   git clone https://github.com/your-username/your-repository.git
   cd your-repository
   ```

2. **Set up MySQL Database**:
    - Create a database:
      
      CREATE DATABASE reservation_system;
    

3. **Configure `application.properties`** for each microservice with your MySQL credentials.

4. **Build and Run each Microservice**:
   Use Maven to build and run the microservices:
 
   mvn spring-boot:run


5. **Access APIs**:
    - Test the APIs using Postman or any REST client:
        - **User Service**: `http://localhost:8081/users`
        - **Reservation Service**: `http://localhost:8082/reservations`
        - **Catalog Service**: `http://localhost:8083/catalog`
        - **Admin Service**: `http://localhost:8084/admin`

---

## Security

- **Spring Security** is integrated to handle user authentication and authorization.
- **JWT (JSON Web Tokens)** is used to secure API endpoints and manage user sessions.
- Different user roles (Admin, Producer, Critic, Member) determine access to specific resources and actions.

---

-end structure, technologies, and setup for your project, providing clear instructions for developers to understand and run the system.