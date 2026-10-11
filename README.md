# Smart University Management System

A role-based university portal built with Spring Boot. Students, teachers and admins each get a different experience: what a user sees and what they can do changes with their role (role-based access control).

## Features

### Role-Based Access Control (RBAC)
Access is controlled with **Spring Security** and **JWT**. The role inside the token decides which endpoints and screens a user can reach.

**Student**
- Log in securely and stay signed in automatically with JWT
- Register for courses and access course files
- View results
- Receive **AI-generated performance suggestions** powered by Gemini
- Access the fee portal

**Teacher**
- Log in and access their assigned courses and files
- Upload student results
- Cannot enroll themselves in a course. Only an admin can enroll teachers

**Admin**
- Create courses
- Enroll teachers into courses
- Manage the portal's users and courses

### AI-Powered Feedback
Integrates the **Gemini AI service** to generate automated feedback and suggestions based on a student's performance.

### Event-Driven Architecture
Uses **Apache Kafka (KRaft mode)** for asynchronous, decoupled communication between services.

### Deployment
- Services run in **Docker** across multiple Docker Compose files with shared networking
- **AWS S3** for persistent file storage

## Tech Stack
Java, Spring Boot, Spring Security, JWT, MySQL, Apache Kafka (KRaft), Docker and Docker Compose, AWS S3, Gemini API

## Roles and Access

| Feature | Student | Teacher | Admin |
|---|---|---|---|
| Log in with JWT | ✅ | ✅ | ✅ |
| Register for courses | ✅ | ❌ | ❌ |
| View results | ✅ | ❌ | ❌ |
| AI performance suggestions | ✅ | ❌ | ❌ |
| Fee portal | ✅ | ❌ | ❌ |
| Upload results | ❌ | ✅ | ❌ |
| Access course files | ✅ | ✅ | ✅ |
| Create courses | ❌ | ❌ | ✅ |
| Enroll teachers | ❌ | ❌ | ✅ |

## Getting Started

### Prerequisites
- Docker and Docker Compose
- A Gemini API key
- AWS credentials for S3

### Run
1. Clone the repository:
   `git clone https://github.com/AbdulRafay-00/Smart-University-Management-System.git`
2. Create a `.env` file with your configuration (database credentials, JWT secret, Gemini API key, AWS credentials).
3. Start the application:
   `docker compose up --build`
4. The app runs at `http://localhost:8080`.

## Author
**Abdul Rafay**: [LinkedIn](https://www.linkedin.com/in/abdulrafay-ubit/) | [GitHub](https://github.com/AbdulRafay-00)
