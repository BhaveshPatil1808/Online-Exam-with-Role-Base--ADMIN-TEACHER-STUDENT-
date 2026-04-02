# 📝 Online Exam System

[![Java](https://img.shields.io/badge/Java-21-blue?logo=java)](https://www.oracle.com/java/)
[![JDBC](https://img.shields.io/badge/JDBC-Database%20Connectivity-green)](https://docs.oracle.com/javase/8/docs/technotes/guides/jdbc/)
[![Database](https://img.shields.io/badge/Database-MySQL-lightblue?logo=mysql)](https://www.mysql.com/)

A **Console-based Online Exam System** built with **Java, JDBC, and MySQL**.  
It allows **Students** to take exams, **Teachers** to add/manage questions, and **Admins** to view results and oversee the system.

---

## 🛠 Tech Stack
- ☕ **Java 21**
- 🔗 **JDBC** (Database connectivity)
- 🗄 **MySQL Database**
- 🖥 **Console-based UI**

---

## 📦 Features
- 👤 **User Registration & Login** (roles: Admin, Teacher, Student)  
- 📋 **Exam Management** (students can take exams, answers are auto‑evaluated)  
- ➕ **Question Management** (teachers can add/view questions)  
- 📊 **Result Tracking** (results saved with score, total questions, date)  
- 🔐 **Role-based Menus** (different options for Admin, Teacher, Student)  

---

## ⚙️ Prerequisites
- Java 21+  
- MySQL running locally  
- JDBC driver (MySQL Connector/J)  

---

## 🚀 Getting Started

1️⃣ **Clone the repository**
```bash
git clone https://github.com/BhaveshPatil1808/Online-Exam-System.git
cd Online-Exam-System


## 2️⃣ Configure Database  
Update DBConnection.java with your DB credentials:
String username = "root";
String password = "yourpassword";
String url = "jdbc:mysql://localhost:3306/online_exam";

## 3️⃣ Create Database Schema
CREATE DATABASE online_exam;

USE online_exam;

CREATE TABLE users (
  id INT PRIMARY KEY AUTO_INCREMENT,
  username VARCHAR(50) UNIQUE NOT NULL,
  password VARCHAR(50) NOT NULL,
  role VARCHAR(20) NOT NULL
);

CREATE TABLE questions (
  id INT PRIMARY KEY AUTO_INCREMENT,
  question TEXT NOT NULL,
  option1 VARCHAR(100),
  option2 VARCHAR(100),
  option3 VARCHAR(100),
  option4 VARCHAR(100),
  correctAns INT NOT NULL
);

CREATE TABLE results (
  id INT PRIMARY KEY AUTO_INCREMENT,
  user_id INT,
  score INT,
  totalQuestions INT,
  examDate DATE,
  FOREIGN KEY (user_id) REFERENCES users(id)
);

## 4️⃣ Compile the project
javac -d bin src/com/onlineExam/**/*.java

## 5️⃣ Run the application
java -cp bin com.onlineExam.Main.MainApp

## 💬 Usage (CLI Menus)
**👤 Student Menu**

Take Exam

View My Results

**👨‍🏫 Teacher Menu**

Add Question

View All Questions

View Results

**👨‍💻 Admin Menu**

View All Questions

View All Results

## 📂 Project Structure
## 📁 Project Structure

```
Online-Exam-System/
│
├── com.onlineExam.DAO/           # Data Access Layer (QuestionDAO, ResultDAO, UserDAO)
├── com.onlineExam.DBConnection/  # Database connection utility
├── com.onlineExam.Entity/        # Entity classes (Users, Questions, Result)
├── com.onlineExam.Service/       # Business logic & service implementations
├── com.onlineExam.Utility/       # Utility classes (CLI menus, helpers)
└── com.onlineExam.Main/          # Main application entry point
```
## 🚀 Future Improvements

🌐 Add web-based UI (Spring Boot + Thymeleaf)

🔐 Encrypt passwords for security

📊 Add analytics dashboard for results

🐳 Dockerize for deployment

🎯 Add timed exams and multiple subjects

## 👨‍💻 Author
**Bhavesh Patil**
