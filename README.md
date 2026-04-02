# 📝 Online Exam System

[![Java](https://img.shields.io/badge/Java-21-blue?logo=java)](https://www.oracle.com/java/)
[![JDBC](https://img.shields.io/badge/JDBC-Database%20Connectivity-green)](https://docs.oracle.com/javase/8/docs/technotes/guides/jdbc/)
[![Database](https://img.shields.io/badge/Database-MySQL-lightblue?logo=mysql)](https://www.mysql.com/)

A **console-based Online Exam System** built using **Java, JDBC, and MySQL**.
It allows:

* 👨‍🎓 Students to take exams
* 👨‍🏫 Teachers to manage questions
* 👨‍💻 Admins to monitor results

---

## 🛠 Tech Stack

* ☕ Java 21
* 🔗 JDBC (Database Connectivity)
* 🗄 MySQL Database
* 🖥 Console-based UI

---

## 📦 Features

* 👤 **User Registration & Login** (Admin, Teacher, Student)
* 📋 **Exam Management** (auto-evaluation of answers)
* ➕ **Question Management** (add/view questions)
* 📊 **Result Tracking** (score, total questions, exam date)
* 🔐 **Role-Based Access Control**

---

## ⚙️ Prerequisites

* Java 21+
* MySQL installed and running
* MySQL Connector/J (JDBC Driver)

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
[git clone https://github.com/BhaveshPatil1808/Online-Exam-System.git](https://github.com/BhaveshPatil1808/Online-Exam-with-Role-Base--ADMIN-TEACHER-STUDENT-.git)

```

---

### 2️⃣ Configure Database

Update `DBConnection.java`:

```java
String username = "root";
String password = "yourpassword";
String url = "jdbc:mysql://localhost:3306/online_exam";
```

---

### 3️⃣ Create Database Schema

```sql
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
```

---

### 4️⃣ Compile the Project

```bash
javac -d bin src/com/onlineExam/**/*.java
```

---

### 5️⃣ Run the Application

```bash
java -cp bin com.onlineExam.Main.MainApp
```

---

## 💬 Usage (CLI Menus)

### 👨‍🎓 Student Menu

* Take Exam
* View My Results

### 👨‍🏫 Teacher Menu

* Add Question
* View All Questions
* View Results

### 👨‍💻 Admin Menu

* View All Questions
* View All Results

---

## 📂 Project Structure

```bash
Online-Exam-System/
│
├── com.onlineExam.DAO/           # Data Access Layer (QuestionDAO, ResultDAO, UserDAO)
├── com.onlineExam.DBConnection/  # Database connection utility
├── com.onlineExam.Entity/        # Entity classes (Users, Questions, Result)
├── com.onlineExam.Service/       # Business logic & service implementations
├── com.onlineExam.Utility/       # Utility classes (CLI menus, helpers)
└── com.onlineExam.Main/          # Main application entry point
```

---

## 🚀 Future Improvements

* 🌐 Web-based UI (Spring Boot + Thymeleaf)
* 🔐 Password encryption
* 📊 Analytics dashboard
* 🐳 Docker support
* ⏱ Timed exams & multiple subjects

---

## 👨‍💻 Author

**Bhavesh Patil**
