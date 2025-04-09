# Student Course Management System

A simple student course management system built using **Spring Boot, Java, and MySQL**.

## Features
- User authentication (login/logout)
- Manage student details (ID, name, course, and fees)
- CRUD operations for students
- Secure database integration with MySQL

## Tech Stack
- **Backend:** Java, Spring Boot
- **Database:** MySQL

## Database Schema
**Database Name:** `lindaschool`

### Tables
#### `login`
| Column   | Type    |
|----------|--------|
| username | VARCHAR |
| password | VARCHAR |

#### `student`
| Column  | Type    |
|---------|--------|
| id      | INT (PK) |
| name    | VARCHAR |
| course  | VARCHAR |
| fees    | DECIMAL |

## Installation
1. **Clone the Repository**
   ```sh
   git clone https://github.com/yourusername/student-course-management.git
   cd student-course-management
   ```
2. **Set Up MySQL Database**
   ```sql
   CREATE DATABASE lindaschool;
   USE lindaschool;
   CREATE TABLE login (
       username VARCHAR(50) PRIMARY KEY,
       password VARCHAR(255) NOT NULL
   );
   CREATE TABLE student (
       id INT PRIMARY KEY AUTO_INCREMENT,
       name VARCHAR(100) NOT NULL,
       course VARCHAR(100) NOT NULL,
       fees DECIMAL(10,2) NOT NULL
   );
   ```
3. **Configure `application.properties`**
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/lindaschool
   spring.datasource.username=root
   spring.datasource.password=yourpassword
   spring.jpa.hibernate.ddl-auto=update
   ```
4. **Run the Application**
   ```sh
   mvn spring-boot:run
   ```

## API Endpoints
| Method | Endpoint        | Description |
|--------|----------------|-------------|
| POST   | `/login`       | Authenticate user |
| GET    | `/students`    | Get all students |
| GET    | `/students/{id}` | Get student by ID |
| POST   | `/students`    | Add a new student |
| PUT    | `/students/{id}` | Update student details |
| DELETE | `/students/{id}` | Delete a student |

demo
