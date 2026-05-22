# 🎓 AlumVerse — Alumni Management System

A full-stack web application to connect, manage, and engage college alumni. Built with **Spring Boot** (backend) and **HTML/CSS/JavaScript** (frontend).

![Java](https://img.shields.io/badge/Java-21-orange?style=flat-square&logo=java)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.5-brightgreen?style=flat-square&logo=springboot)
![MySQL](https://img.shields.io/badge/MySQL-Database-blue?style=flat-square&logo=mysql)
![Maven](https://img.shields.io/badge/Maven-Build-red?style=flat-square&logo=apachemaven)
![Chart.js](https://img.shields.io/badge/Chart.js-Visualization-pink?style=flat-square&logo=chartdotjs)

---

## 📌 Features

### 👤 Authentication
- Secure login with role-based access — **ADMIN** and **USER**
- Protected pages redirect to login if not authenticated
- Logout functionality

### 🔍 Discover Alumni
- Browse all registered alumni
- Search and filter by name, batch year, department, company, or location
- Send connection requests to other alumni
- **ADMIN only:** Add and delete alumni records

### 💼 Job Board
- Any logged-in alumni can post job openings
- Filter jobs by title, company, or type (Full-Time / Internship / Remote / Contract)
- Apply directly via email link
- **ADMIN only:** Delete job postings

### 👤 My Profile
- View and edit personal profile (name, batch, department, company, location, bio, LinkedIn)
- View your connections list

### 📊 Admin Dashboard *(ADMIN only)*
- Live stats: Total Alumni, Total Users, Job Postings, Latest Batch
- Dynamic charts via Chart.js: Alumni by Batch Year, by Department, Top Locations, Top Companies
- Recent alumni table with delete option
- Export all alumni data to **CSV**

### 📰 News & Events
- Latest college news, announcements, and upcoming events

### 🏆 Achievements
- Spotlight on notable alumni achievements and milestones

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Language** | Java 21 |
| **Backend** | Spring Boot 3.5 |
| **Frontend** | HTML, CSS, JavaScript |
| **Database** | MySQL |
| **ORM** | Spring Data JPA / Hibernate |
| **Build Tool** | Maven |
| **Charts** | Chart.js |
| **Utilities** | Lombok |
| **Version Control** | Git & GitHub |

---

## 📁 Project Structure

```
Alumni-Management-System/
├── src/
│   └── main/
│       ├── java/alumni_management/
│       │   ├── controller/
│       │   │   ├── AlumniController.java   # Alumni CRUD APIs
│       │   │   ├── AuthController.java     # Login & user count APIs
│       │   │   └── JobController.java      # Job board APIs
│       │   ├── model/
│       │   │   ├── Alumni.java             # Alumni entity
│       │   │   ├── User.java               # User entity
│       │   │   └── Job.java                # Job entity
│       │   └── repository/
│       │       ├── AlumniRepository.java
│       │       ├── UserRepository.java
│       │       └── JobRepository.java
│       └── resources/
│           ├── static/
│           │   ├── login.html              # Login page
│           │   └── Prototype.html          # Main app UI
│           └── application.properties      # DB & server config
└── pom.xml
```

---

## ⚙️ Setup & Run

### Prerequisites
- Java 17+
- Maven
- MySQL

### 1. Clone the repository
```bash
git clone https://github.com/pawan0221/Alumni-Management-System-.git
cd Alumni-Management-System-
```

### 2. Configure the database
Create a MySQL database named `alumnidb`, then set environment variables:

```bash
SPRING_DATASOURCE_URL=jdbc:mysql://localhost:3306/alumnidb
SPRING_DATASOURCE_USERNAME=root
SPRING_DATASOURCE_PASSWORD=yourpassword
```

Or directly edit `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/alumnidb
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
```

### 3. Run the application
```bash
./mvnw spring-boot:run
```

### 4. Open in browser
```
http://localhost:8080/login.html
```

---

## 🔑 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/auth/login` | Login with username & password |
| `GET` | `/auth/users/count` | Get total user count |
| `GET` | `/alumni` | Get all alumni |
| `POST` | `/alumni` | Add new alumni |
| `DELETE` | `/alumni/{id}` | Delete alumni by ID |
| `GET` | `/alumni/count` | Get total alumni count |
| `GET` | `/jobs` | Get all job postings |
| `POST` | `/jobs` | Post a new job |
| `DELETE` | `/jobs/{id}` | Delete job by ID |

---

## 🚀 Roles & Access

| Feature | User | Admin |
|---|---|---|
| Login / Logout | ✅ | ✅ |
| Browse Alumni | ✅ | ✅ |
| Send Connections | ✅ | ✅ |
| Post Jobs | ✅ | ✅ |
| Edit Profile | ✅ | ✅ |
| Add Alumni | ❌ | ✅ |
| Delete Alumni | ❌ | ✅ |
| Delete Jobs | ❌ | ✅ |
| Admin Dashboard | ❌ | ✅ |
| Export CSV | ❌ | ✅ |
---
👨‍💻 Developers
Nischay Jain — @nischayj
Pawan Soni — @pawan0221
---
## 📄 License

This project is for educational purposes.
