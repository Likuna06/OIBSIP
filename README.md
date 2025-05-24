# 🧠 Online Examination System (Java + MySQL)

This project is a **Java Swing-based Online Examination System** with **MySQL** as the backend. Developed during my internship at **Oasis Infobyte**, the system simulates a complete examination environment with login, timed questions, and detailed result analysis.

---

## 📁 Project Structure

```
OIBSIP/
└── TASK2/
    └── OnlineExaminationSystem/
        ├── src/
        │   └── OnlineExamSystem.java
        ├── sql/
        │   └── OnlineExamDB.sql
        └── README.md
```

---

## ✅ Features

- 🔐 User Login and Registration  
- 📝 Profile Update (Username & Password)  
- ⏳ Timed Quiz: 30 seconds per question  
- 📚 10 Multiple Choice Questions from MySQL  
- 📊 Detailed Result Panel with performance summary  
- 🎨 User-friendly blue color-themed UI (Java Swing)

---

## 🧑‍💻 Tech Stack

| Technology     | Description                  |
|----------------|------------------------------|
| Java (Swing)   | Desktop GUI                  |
| MySQL          | Database backend             |
| JDBC           | Java Database Connectivity   |
| IntelliJ/Eclipse | Development environment    |

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/OIBSIP.git
cd OIBSIP/TASK2/OnlineExaminationSystem
```

### 2. Import SQL Schema

- Open **MySQL Workbench**
- Execute the SQL file located at `sql/OnlineExamDB.sql`

```sql
CREATE DATABASE IF NOT EXISTS OnlineExamDB;
USE OnlineExamDB;

CREATE TABLE IF NOT EXISTS users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    password VARCHAR(100) NOT NULL
);

CREATE TABLE IF NOT EXISTS questions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    question TEXT NOT NULL,
    option1 VARCHAR(255) NOT NULL,
    option2 VARCHAR(255) NOT NULL,
    option3 VARCHAR(255) NOT NULL,
    option4 VARCHAR(255) NOT NULL,
    correct_option INT NOT NULL CHECK (correct_option BETWEEN 1 AND 4)
);
```

- Insert 10 sample questions for testing.

### 3. Configure Database Connection

In `OnlineExamSystem.java`:

```java
conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/OnlineExamDB", "root", "your_password");
```

### 4. Compile and Run

Use an IDE like IntelliJ or run from terminal:

```bash
javac src/OnlineExamSystem.java
java src.OnlineExamSystem
```

---

## 🎯 How It Works

1. **Register or Login** with credentials
2. **Update profile** info if desired
3. Start the **quiz with 10 questions**
   - Each question has a 30-second timer
   - Automatically submits or can be manually submitted
4. View your **result analysis** with selected and correct answers

---

## 📸 Screenshots

> *(Optional)* Include screenshots showing the login panel, quiz interface, and result panel.

---

## 🎓 Internship Attribution

This project was built as part of my internship with **[Oasis Infobyte](https://oasisinfobyte.com/)** under the Web Development & Designing track. It was an excellent opportunity to apply real-world development practices and strengthen my backend + GUI integration skills.

---

## 📌 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Author

- **[Your Name]** — [GitHub](https://github.com/yourusername)

---

## 🙏 Thank You

Special thanks to **Oasis Infobyte** for the opportunity and guidance.  
This project has enhanced my understanding of Java desktop applications and SQL integration.
