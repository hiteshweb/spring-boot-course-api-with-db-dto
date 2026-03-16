Step 1: Prerequisites
Install the following:

Java Development Kit (JDK): Version 11 or higher
Download from: https://www.oracle.com/java/technologies/downloads/
Verify: java -version
Maven: Version 3.6 or higher
Download from: https://maven.apache.org/download.cgi
Verify: mvn -version
Git: For version control
Download from: https://git-scm.com/
IDE: IntelliJ IDEA, Eclipse, or VS Code
MySQL: Database (optional, can use H2 for in-memory)
Download from: https://www.mysql.com/downloads/

Step 2: Create Project Structure
Option A: Using Spring Boot Initializer (Recommended)
Go to https://start.spring.io/

Fill in the form:

Project: Maven Project
Language: Java
Spring Boot: 3.x (latest stable)
Group: com.example
Artifact: user-management-api
Name: User Management API
Packaging: Jar
Java: 17 or higher
Add Dependencies:

Spring Web
Spring Data JPA
MySQL Driver (or H2 Database for testing)
Lombok (optional, but recommended)
Spring Boot DevTools
Click Generate and download the ZIP file

Extract and open in your IDE

Step 3: Project Structure Setup
After extraction, your project should look like this:

Code
user-management-api/
├── src/
│   ├── main/
│   │   ├── java/com/example/
│   │   │   ├── UserManagementApiApplication.java
│   │   │   ├── controller/
│   │   │   ├── service/
│   │   │   ├── repository/
│   │   │   ├── entity/
│   │   │   ├── dto/
│   │   │   └── exception/
│   │   └── resources/
│   │       ├── application.properties
│   │       └── application-dev.properties
│   └── test/
├── pom.xml
└── README.md


Create DB: CREATE DATABASE user_management;


1. Get All Users (GET)
GET http://localhost:8080/api/users

2. Create User (POST)
POST http://localhost:8080/api/users
Content-Type: application/json

{
  "firstName": "John",
  "lastName": "Doe",
  "email": "john@example.com",
  "phone": "9876543210",
  "address": "123 Main St, City, State"
}

3. Get User by ID (GET)
GET http://localhost:8080/api/users/1

4. Get User by Email (GET)
GET http://localhost:8080/api/users/email/john@example.com

5. Update User (PUT)
PUT http://localhost:8080/api/users/1
Content-Type: application/json

{
  "firstName": "Jane",
  "lastName": "Doe",
  "email": "jane@example.com",
  "phone": "9876543210",
  "address": "456 Oak Ave, City, State"
}

6. Delete User (DELETE)
DELETE http://localhost:8080/api/users/1
