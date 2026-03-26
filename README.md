IDMRS Inventory Management System

IDMRS (Intelligent Data Management and Recommendation System) is a robust, secure, and highly scalable Spring Boot backend built for inventory management. It features JWT-based role-based access control, intelligent recommendation logic, and bulk CSV operations, providing a complete solution for modern inventory demands.

 Features

*   **RESTful API:** Developed with Spring Boot 3.2.4 following best practices and layered architecture.
*   **Security:** Robust JWT-based authentication and authorization using Spring Security.
*   **Database Integration:** Seamless MySQL integration using Spring Data JPA and Hibernate.
*   **Rate Limiting:** Protects endpoints from abuse using Bucket4j.
*   **Caching Strategy:** High-performance local caching using Caffeine.
*   **CSV Processing:** Read, parse, and handle bulk inventory operations with OpenCSV.
*   **API Documentation:** Interactive and beautifully structured Swagger UI powered by Springdoc OpenAPI.
*   **Observability:** Health, info, and metrics monitoring using Spring Boot Actuator.

Tech Stack

*   **Java:** 21
*   **Framework:** Spring Boot 3.2.4
*   **Database:** MySQL Server
*   **ORM:** Hibernate / Spring Data JPA
*   **Security:** Spring Security + io.jsonwebtoken (jjwt 0.12.5)
*   **API Documentation:** Springdoc OpenAPI / Swagger (v2.3.0)
*   **Cache:** Caffeine Cache
*   **Rate Limiting:** Bucket4j
*   **File Parsing:** OpenCSV
*   **Utilities:** Lombok, MapStruct

Prerequisites

*   JDK 21 or higher
*   Maven 3.8.x or higher
*   MySQL 8.x Server running locally (or adjust the properties for a remote DB)

Configuration

Configure the `application.properties` in `src/main/resources` before running the application:

```properties
# MySQL DB configuration
spring.datasource.url=jdbc:mysql://localhost:3306/idmrs_inventory?createDatabaseIfNotExist=true&useSSL=false&serverTimezone=UTC&allowPublicKeyRetrieval=true
spring.datasource.username=root
spring.datasource.password=Rajaram001

# JWT Secret (Must be 256 bits or more for HS256)
app.jwt.secret=idmrs-super-secret-key-must-be-at-least-256-bits-long-for-hs256
```

 Running the Application

1.  **Clone the Repository** and navigate to the project directory:
    ```bash
    cd inventory-project
    ```

2.  **Build the Project:**
    ```bash
    ./mvnw clean install
    # or
    mvn clean install
    ```

3.  **Run the Application:**
    ```bash
    ./mvnw spring-boot:run
    # or
    mvn spring-boot:run
    ```

4.  The server will start on port `8080` with the context path `/api`.

    **Base URL:** `http://localhost:8080/api`

API Documentation (Swagger)

A full interactive API documentation is automatically generated. Once the application is running, you can access Swagger UI here:

*   **Swagger UI:** [http://localhost:8080/api/swagger-ui.html](http://localhost:8080/api/swagger-ui.html)
*   **OpenAPI JSON:** [http://localhost:8080/api/v3/api-docs](http://localhost:8080/api/v3/api-docs)

To test secure endpoints, authenticate via the `/auth/login` endpoint, extract the token, and provide it using the **"Authorize"** button in Swagger UI.

Monitoring & Health

Spring Boot Actuator is configured to provide insights into application health:
*   **Health:** `http://localhost:8080/api/actuator/health`
*   **Info:** `http://localhost:8080/api/actuator/info`
