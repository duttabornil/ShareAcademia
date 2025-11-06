# Module Overview: ShareAcademia

## 1. main.java
**Purpose:**  
Main application entry point and GUI. Implements all logic and user interface, divided into the following modules:

- **GPA Calculator Tab**  
  - Allows calculation of GPA for two semesters.
  - Users select grades and credits for defined subjects.
  - GPA calculation logic (weighted average with grade points).

- **Attendance Management Tab**  
  - Add new students to attendance database.
  - Mark student attendance by ID.
  - View all attendance records.
  - CRUD operations on `attendanceDB.attendance` table via JDBC.

- **PDF Viewer Tab**  
  - Lets users load local PDF files and open/view them.
  - File browsing/selection and system viewer integration.

- **Student Details Tab**  
  - Add new student details (name, id, age, gpa, contact, department, address).
  - View all student details.
  - CRUD operations on `studentDetailsDB.studentDetails` table via JDBC.

## 2. SQL Code (sql_code.txt)
**Purpose:**
- Provides DDL scripts to set up the databases and tables.
- Inserts sample student records.

**Key Tables:**
- `studentDetailsDB.studentDetails` (id, name, age, gpa, contact, department, address)
- `attendanceDB.attendance` (id, name, attendance_count) — presumed from code, not explicitly found in sql_code.txt

## 3. Dependencies (requirements.txt)
**Purpose:**
- Lists required libraries for compilation and runtime.
- Java core libraries: `javax.swing`, `java.awt`, `java.sql`
- JDBC connector: `mysql:mysql-connector-java:8.0.33`

## 4. Configuration
**Where:**  
Database credentials are hardcoded in main.java:
- Username/password variables (must be user-edited)
- MySQL connection URLs for both databases

## 5. Documentation (README.md)
**Purpose:**  
Describes setup, features, project structure, dependencies, and future plans.

---

## High-Level Flow

1. **User interacts with main GUI.**
2. **Data entered or requested is sent to MySQL DB using JDBC.**
3. **DB responses used to update GUI.**
4. **PDF viewer operates locally, not via database.**

## NOTE
- All modules are encapsulated in one file (main.java), but modularized as Java methods and tabs.
- No external API calls; all logic is local or uses MySQL.