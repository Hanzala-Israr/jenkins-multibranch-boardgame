#  Boardgame Listing Web Application with Jenkins CI/CD

## 📌 Project Overview

**Boardgame Listing Web App** is a **full-stack web application** that allows users to explore board games and read reviews. The application implements **role-based authentication and authorization**, enabling different users to interact with the system based on their permissions.

The project also demonstrates a **DevOps CI/CD pipeline** using **Jenkins Multibranch Pipeline**, **GitHub Webhooks**, and **automated build/testing workflows**.

The main goal of this project is to combine **full-stack development with modern DevOps practices**.

---

# 🚀 Key Features

### 🎮 Application Features

- View a list of board games and reviews
- Add new board games
- Write reviews for board games
- Edit and delete reviews (manager role only)
- Secure login and authentication
- Role-based access control
- Clean UI using Thymeleaf templates and Bootstrap

---

### 🔐 Role-Based Access

| Role | Permissions |
|-----|-------------|
| **Non-Member** | View board games and reviews |
| **User** | Add board games and write reviews |
| **Manager** | Edit and delete reviews |

Authentication and authorization are implemented using **Spring Security**.

---

# 🛠️ Technologies Used

## Backend

- Java
- Spring Boot
- Spring MVC
- Spring Security
- JDBC

## Frontend

- Thymeleaf
- Thymeleaf Fragments
- HTML5
- CSS
- JavaScript
- Twitter Bootstrap

## Database

- H2 Database Engine (In-memory)

## Testing

- JUnit

## DevOps & Deployment

- Jenkins
- Jenkins Multibranch Pipeline
- GitHub Webhooks
- Maven
- AWS EC2

---

#  Application Architecture

The project follows **Spring MVC architecture** with clear separation of concerns:

Controller Layer
        ↓
Service Layer
        ↓
Repository / JDBC Layer
        ↓
H2 Database

### Main Components

- **Controllers** – Handle HTTP requests
- **Services** – Business logic
- **Repositories** – Database operations
- **Views** – Thymeleaf templates

---

# ☁️ Deployment

The application is deployed on:

**Amazon Web Services (AWS) EC2**

Steps performed:

1. Launch EC2 instance
2. Install Java and Maven
3. Clone project repository
4. Build the project
5. Run Spring Boot application

---

# ⚙️ CI/CD Pipeline with Jenkins

This project uses **Jenkins Multibranch Pipeline** to automate the build and testing process.

## Pipeline Workflow

Developer pushes code to GitHub
        
↓
        
GitHub Webhook triggers Jenkins
        
↓
        
Jenkins detects branch
        
↓
        
Jenkins Multibranch Pipeline runs
        
↓
        
Maven builds the project
        
↓
        
JUnit tests are executed
        
↓
        
Build status and notifications are generated

---

# 🌿 Jenkins Multibranch Pipeline

A **Multibranch Pipeline** automatically creates pipelines for each branch in the repository.

### Benefits

- Automatic branch discovery
- Parallel development workflows
- Independent builds for each branch
- Automatic pipeline execution

Example branches:

main
develop
feature/login
feature/reviews

Each branch triggers its own pipeline build.

---

# 🔔 GitHub Webhooks Integration

**GitHub Webhooks** are configured to notify Jenkins whenever code changes occur.

### Workflow

1️⃣ Developer pushes code to GitHub  
2️⃣ GitHub sends webhook event to Jenkins  
3️⃣ Jenkins triggers pipeline automatically  
4️⃣ Jenkins runs build and tests

Webhook events include:

- push
- pull request updates
- branch creation

---

# 📢 Jenkins Notifications

Notifications can be configured to inform the team about:

- Build success
- Build failure
- Pipeline execution results

Common notification channels:

- Email
- Slack
- Jenkins dashboard alerts

---

# ▶️ How to Run the Project

### 1️⃣ Clone the repository

git clone https://github.com/your-username/boardgame-jenkins-pipeline.git

---

### 2️⃣ Navigate to project directory

cd boardgame-jenkins-pipeline

---

### 3️⃣ Build the project

mvn clean install

---

### 4️⃣ Run the application

mvn spring-boot:run

---

### 5️⃣ Access the application

Open browser:

http://localhost:8080

---

# 👤 Default User Credentials

Initial users included in the database:

| Username | Password | Role |
|--------|--------|------|
| bugs | bunny | User |
| daffy | duck | Manager |

You can also register new users.

---

# 🧪 Testing

Unit tests are written using **JUnit**.

Run tests using:

mvn test

---

# 📊 CI/CD Benefits in This Project

- Automated builds
- Automated testing
- Faster development cycle
- Reduced manual deployment errors
- Continuous integration of code changes

---


# 👨‍💻 Author

**Hanzala Israr**  
