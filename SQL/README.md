
# 📊 Student Performance Analysis – SQL

### 🗄️ SQL Data Analysis Project

**Analyze • Query • Compare • Extract Insights**
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/86e0e407-d0cb-4d6a-8816-8597972291fc" />

<p align="center">

### 🖱️ Click the Image Above

<p align="center">

<a href="#-project-overview">
💡 <b>PROJECT OVERVIEW</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-main-objectives">
🎯 <b>MAIN OBJECTIVES</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-technologies-used">
🛠️ <b>TECHNOLOGIES</b>
</a>

</p>

<p align="center">

<a href="#-database-creation">
🗄️ <b>DATABASE</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-analytical-queries">
📊 <b>ANALYTICAL QUERIES</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-sql-concepts-demonstrated">
🧠 <b>SQL CONCEPTS</b>
</a>

</p>

<p align="center">

<a href="#-analysis-highlights">
📈 <b>ANALYSIS</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-skills-demonstrated">
💼 <b>SKILLS</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-interview-explanation">
🎓 <b>INTERVIEW</b>
</a>

</p>


### 🗄️ SQL Data Analysis Project

**Analyze • Query • Compare • Extract Insights**

</p>

---

## 🏷️ Skills Badges

<p align="center">

![SQL](https://img.shields.io/badge/SQL-Data%20Analysis-blue?style=for-the-badge\&logo=mysql)
![MySQL](https://img.shields.io/badge/MySQL-Database-orange?style=for-the-badge\&logo=mysql)
![Database](https://img.shields.io/badge/Database-Management-green?style=for-the-badge)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-Insights-purple?style=for-the-badge)

</p>

---

## 📌 Project Overview

This project performs **Student Performance Analysis using SQL**. 📊

The project creates a database, stores student assessment and course information, and uses SQL queries to analyze performance across **departments, courses, and sessions**. 🗄️📈

### 🎯 Main Objectives

* 🗄️ Create a SQL database
* 📋 Create `assessments` and `courses` tables
* 📥 Insert assessment and course data
* 🔗 Join related tables using `course_id`
* 📊 Calculate average scores by department
* 📚 Identify underperforming courses
* 🏆 Find top two sessions by average score
* 🔍 Use `GROUP BY`, `AVG()`, `HAVING`, `ORDER BY`, and `LIMIT`
* 💡 Generate meaningful performance insights

---

## 🎯 Project Goal

The main goal of this project is to transform **student performance data into meaningful SQL-based insights**. 🚀

* 🏢 Understand department-wise performance
* 📚 Analyze course-wise average scores
* 📉 Identify courses with lower average performance
* 🏆 Compare different sessions/batches
* 🔗 Practice SQL table relationships and joins
* 📊 Use aggregation functions for data analysis
* 💡 Convert raw database records into useful insights

### 💡 Overall Goal

**Raw Data → SQL Queries → Analysis → Insights** 📊🚀

---

## 🛠️ Technologies Used

| 🧰 Technology              | 🎯 Purpose                    |
| -------------------------- | ----------------------------- |
| 🗄️ **SQL**                | Database querying & analysis  |
| 🐬 **MySQL**               | Database management           |
| 📊 **Aggregate Functions** | Calculate average performance |
| 🔗 **JOIN**                | Combine related tables        |
| 📋 **GROUP BY**            | Group records for analysis    |
| 🔍 **HAVING**              | Filter grouped results        |
| 📈 **ORDER BY**            | Sort analytical results       |
| 🔢 **LIMIT**               | Retrieve top results          |

---

## 🔄 Project Workflow

```text
🗄️ Create Database
       ↓
📋 Create Tables
       ↓
📥 Insert Data
       ↓
🔍 View Data
       ↓
🔗 Join Tables
       ↓
📊 Calculate Average Scores
       ↓
📉 Find Underperforming Courses
       ↓
🏆 Find Top Sessions
       ↓
💡 Generate Insights
```

---

## 🎬 Project Preview

> 📌 Add your SQL project GIF inside the `outputs` folder.

<p align="center">
  <img src="outputs/sql_analysis.gif" alt="SQL Data Analysis Preview" width="850">
</p>

### 📁 GIF Location

```text
outputs/sql_analysis.gif
```

---

## 🗄️ Database Creation

The project starts by creating the SQL database:

```sql
CREATE DATABASE sql____db;
```

---

## 📋 Table 1 — Assessments

The `assessments` table stores student assessment and performance information.

### 📌 Columns

| Column          | Description             |
| --------------- | ----------------------- |
| 🆔 `id`         | Unique assessment ID    |
| 📅 `month`      | Assessment month        |
| 🔗 `course_id`  | Course identifier       |
| 🕐 `session`    | Assessment session      |
| 📝 `marks1`     | Assessment score        |
| 📝 `marks2`     | Second assessment score |
| 🏢 `department` | Student department      |
| 🎯 `pass_flag`  | Pass/Fail indicator     |

```sql
CREATE TABLE assessments (
    id INT PRIMARY KEY,
    month VARCHAR(50),
    course_id VARCHAR(10),
    session VARCHAR(10),
    marks1 INT,
    marks2 INT,
    department VARCHAR(55),
    pass_flag INT
);
```

---

## 📚 Table 2 — Courses

The `courses` table stores course and department information.

### 📌 Columns

| Column          | Description      |
| --------------- | ---------------- |
| 🔗 `course_id`  | Unique course ID |
| 📖 `course`     | Course name      |
| 🏢 `department` | Department name  |

```sql
CREATE TABLE courses (
    course_id VARCHAR(20) PRIMARY KEY,
    course VARCHAR(50),
    department VARCHAR(55)
);
```

---

## 🔗 Relationship Between Tables

The two tables are connected using:

```text
assessments.course_id
        ↕
courses.course_id
```

This relationship allows the project to combine **assessment performance with course information**. 🔗📊

---

# 📊 Analytical Queries

## 1️⃣ Average Score by Department 🏢

This query calculates the average `marks1` score for each department.

```sql
SELECT 
    c.department,
    AVG(a.marks1) AS avg_score
FROM assessments a
JOIN courses c
    ON a.course_id = c.course_id
GROUP BY c.department
ORDER BY avg_score ASC;
```

### 🔍 SQL Concepts Used

* 🔗 `JOIN`
* 📊 `AVG()`
* 📋 `GROUP BY`
* 📈 `ORDER BY`

### 💡 Purpose

To compare average student performance between departments.

---

## 2️⃣ Underperforming Courses 📉

This query identifies courses with an average `marks1` score below **60**.

```sql
SELECT 
    c.course,
    AVG(a.marks1) AS avg_score
FROM assessments a
JOIN courses c
    ON a.course_id = c.course_id
GROUP BY c.course
HAVING AVG(a.marks1) < 60
ORDER BY avg_score ASC;
```

### 🔍 SQL Concepts Used

* 🔗 `JOIN`
* 📊 `AVG()`
* 📋 `GROUP BY`
* 🎯 `HAVING`
* 📈 `ORDER BY`

### 💡 Purpose

To identify courses where the average score is below the defined threshold.

---

## 3️⃣ Top Two Sessions by Average Score 🏆

This query finds the top two sessions based on average `marks1` score.

```sql
SELECT 
    session AS batch,
    AVG(marks1) AS avg_score
FROM assessments
GROUP BY session
ORDER BY avg_score DESC, batch ASC
LIMIT 2;
```

### 🔍 SQL Concepts Used

* 📊 `AVG()`
* 📋 `GROUP BY`
* 📈 `ORDER BY`
* 🔢 `LIMIT`

### 💡 Purpose

To compare sessions and retrieve the two sessions with the highest average score.

---

## 🧠 SQL Concepts Demonstrated

| 🔧 SQL Concept    | 📌 Usage                  |
| ----------------- | ------------------------- |
| `CREATE DATABASE` | 🗄️ Create database       |
| `CREATE TABLE`    | 📋 Create tables          |
| `INSERT INTO`     | 📥 Insert records         |
| `SELECT`          | 🔍 Retrieve data          |
| `JOIN`            | 🔗 Combine tables         |
| `AVG()`           | 📊 Calculate average      |
| `GROUP BY`        | 📋 Group records          |
| `HAVING`          | 🎯 Filter grouped results |
| `ORDER BY`        | 📈 Sort results           |
| `LIMIT`           | 🏆 Get top records        |

---

## 📈 Analysis Highlights

### 🏢 Department Analysis

Compare the average assessment scores between **Business** and **Technology** departments.

### 📚 Course Analysis

Identify courses where the average `marks1` score is below **60**.

### 🕐 Session Analysis

Compare **Morning, Evening, and Weekend** sessions and retrieve the top two based on average score.

---

## 📁 Project Structure

```text
SQL/
│
├── 📄 sqlpro.sql
├── 📖 README.md
│
└── 📁 outputs/
    └── 🎬 sql_analysis.gif
```

---

## ▶️ How to Run

### 1️⃣ Open MySQL

Open **MySQL Workbench**, **XAMPP/phpMyAdmin**, or another SQL environment.

### 2️⃣ Open SQL File

Open:

```text
sqlpro.sql
```

### 3️⃣ Execute Database Creation

Run the database creation query first.

### 4️⃣ Create Tables

Execute the `CREATE TABLE` statements.

### 5️⃣ Insert Data

Run the `INSERT INTO` statements.

### 6️⃣ Run Analytical Queries

Execute the three analysis queries one by one.

### 7️⃣ Review Results

Analyze the department, course, and session performance results. 📊

---

## 💼 Skills Demonstrated

* 🗄️ SQL Database Management
* 📋 Table Creation
* 📥 Data Insertion
* 🔗 INNER JOIN
* 📊 Aggregate Functions
* 📈 `AVG()`
* 📋 `GROUP BY`
* 🎯 `HAVING`
* 📈 `ORDER BY`
* 🔢 `LIMIT`
* 🔍 Data Filtering
* 📊 Performance Analysis
* 💡 Business/Data Insights

---

## 🎓 Interview Explanation

### 💬 Project: Student Performance Analysis using SQL

> "I created a Student Performance Analysis project using SQL. I created an SQL database with assessments and courses tables and inserted student performance data. I used JOIN to connect the tables through course_id. Then I calculated average scores by department, identified underperforming courses using HAVING, and found the top two sessions using GROUP BY, ORDER BY, and LIMIT. This project helped me practice SQL querying, aggregation, joins, filtering, and data analysis."

---

## 🧪 Practical SQL Skills

### 🔹 JOIN

Used to combine assessment information with course information.

### 🔹 GROUP BY

Used to group data by department, course, or session.

### 🔹 AVG()

Used to calculate average student scores.

### 🔹 HAVING

Used to filter grouped results based on average score.

### 🔹 ORDER BY

Used to sort results from highest to lowest or lowest to highest.

### 🔹 LIMIT

Used to return only the required number of records.

---






## 👨‍💻 Author

### **Rahul Zala**

**Skills:** 🐍 Python • 🗄️ SQL • 📊 Excel • 📈 Power BI • 📊 Data Analysis

---

## ⭐ Project Support

If you find this project useful, please consider giving the repository a **⭐ Star** on GitHub.

### 🙌 Thank You!

**Keep Learning • Keep Building • Keep Analyzing 📊🚀**
