# University Management System

![Java](https://img.shields.io/badge/Java-SE_8%2B-orange?style=flat-square&logo=java)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=flat-square&logo=mysql)
![Swing](https://img.shields.io/badge/UI-Java_Swing-lightgrey?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

> A Java Swing desktop application for university administration — managing students, faculty, leave records, examination marks, and fee structures via a MySQL relational database backend.

---

## 🎯 Features

- **Login system** — credential-based admin authentication
- **Student management** — add, view, update student records with auto-generated roll numbers
- **Faculty management** — add, view, update teacher records
- **Leave management** — apply and view leave records for both students and faculty
- **Examination module** — enter marks and view examination results per semester
- **Fee management** — view course-wise fee structure and student fee forms
- **Utility tools** — embedded Calculator and Notepad launcher

---

## 🏗️ System Architecture

```
Java Swing GUI (Desktop)
        │
        ▼
   Conn.java (JDBC)
        │
        ▼
MySQL Database: universitymanagement
  ├── login          (admin credentials)
  ├── student        (student records)
  ├── teacher        (faculty records)
  ├── studentleave   (student leave logs)
  ├── teacherleave   (faculty leave logs)
  ├── subject        (subjects per semester)
  ├── marks          (exam marks per semester)
  ├── fee            (course fee structure)
  └── feecollege     (student fee collection)
```

---

## 📁 Project Structure

```
University_Management_System/
│
├── src/
│   └── university/management/system/
│       ├── main_class.java         # Main dashboard with menu bar
│       ├── Login.java              # Admin login screen
│       ├── Conn.java               # JDBC MySQL connection
│       ├── AddStudent.java         # Add new student form
│       ├── AddFaculty.java         # Add new faculty form
│       ├── StudentDetails.java     # View student records
│       ├── TeacherDetails.java     # View faculty records
│       ├── StudentLeave.java       # Apply student leave
│       ├── TeacherLeave.java       # Apply faculty leave
│       ├── StudentLeaveDetails.java# View student leave records
│       ├── TeacherLeaveDetails.java# View faculty leave records
│       ├── updateStudent.java      # Update student details
│       ├── UpdateTeacher.java      # Update faculty details
│       ├── EnterMarks.java         # Enter exam marks
│       ├── ExaminationDetails.java # View examination results
│       ├── FreeStructure.java      # View fee structure
│       ├── StudentFeeForm.java     # Student fee form
│       ├── Marks.java              # Marks utility
│       ├── Splash.java             # Splash screen
│       └── About.java              # About dialog
│
├── src/icon/                       # UI image assets
├── create database universitymanagement.txt  # MySQL setup script
├── mysql-connector-java-8.0.28.jar # JDBC driver
├── jcalendar-tz-1.3.3-4.jar       # Date picker library
├── .gitignore
├── LICENSE
└── README.md
```

---

## ⚙️ Setup & Installation

### Prerequisites
- Java SE 8 or higher
- MySQL Server 8.0
- IntelliJ IDEA (recommended) or any Java IDE

### 1. Clone the Repository
```bash
git clone https://github.com/AmudhanManimaran/University-Management-System.git
```

### 2. Set Up the Database
Open MySQL and run the setup script:
```bash
mysql -u root -p < "create database universitymanagement.txt"
```
Or copy-paste the contents into MySQL Workbench / CLI.

### 3. Configure Database Credentials
Open `Conn.java` and update credentials to match your MySQL setup:
```java
connection = DriverManager.getConnection(
    "jdbc:mysql:///universitymanagement", "root", "YOUR_PASSWORD"
);
```

### 4. Add Required JARs to Project Classpath
In your IDE, add the following JARs to the project dependencies:
- `mysql-connector-java-8.0.28.jar`
- `jcalendar-tz-1.3.3-4.jar`

### 5. Run the Application
Run `Login.java` as the entry point.

**Default credentials:**
```
Username: Aaditya
Password: cvbn
```

---

## 🚀 Usage

1. Launch via `Login.java`
2. Enter admin credentials
3. Navigate using the menu bar:
   - **New Information** → Add student or faculty
   - **View Details** → View student or faculty records
   - **Apply Leave** → Submit leave for student or faculty
   - **Leave Details** → View submitted leave records
   - **Examination** → Enter marks or view results
   - **Fee Details** → View fee structure or student fee form
   - **Utility** → Open Calculator or Notepad
   - **Exit** → Close the application

---

## 🗃️ Database Schema

| Table | Key Columns |
|-------|-------------|
| login | username, password |
| student | name, rollno, dob, course, branch, aadhar |
| teacher | name, empID, dob, education, department |
| studentleave | rollno, date, time |
| teacherleave | empID, date, time |
| subject | rollno, semester, subj1–subj5 |
| marks | rollno, semester, mrk1–mrk5 |
| fee | course, semester1–semester8 |
| feecollege | rollno, course, branch, semester, total |

---

## ⚠️ Known Limitations

- **SQL Injection** — Login and form queries use string concatenation instead of PreparedStatements. This is a known security limitation of this version.
- **Windows-only utilities** — Calculator and Notepad launch via `calc.exe` / `notepad.exe` — these only work on Windows.
- **Hardcoded credentials** — Database password is hardcoded in `Conn.java`. Use environment variables in production.
- **No password hashing** — Admin passwords stored in plaintext in the database.

---

## 📄 License

This project is licensed under the **MIT License** — see [LICENSE](LICENSE) for details.

---

## 👤 Author

**Amudhan Manimaran**
- 🌐 Portfolio: [amudhanmanimaran.github.io/Portfolio](https://amudhanmanimaran.github.io/Portfolio/)
- 💼 LinkedIn: [linkedin.com/in/amudhan-manimaran-3621bb32a](https://www.linkedin.com/in/amudhan-manimaran-3621bb32a)
- 🐙 GitHub: [github.com/AmudhanManimaran](https://github.com/AmudhanManimaran)
