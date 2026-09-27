
<h1 align="center">🚀 Student Performance Analysis – Python</h1>

<p align="center">
  
</p>

<img width="1671" height="941" alt="image" src="https://github.com/user-attachments/assets/d1b17c1c-b67c-4737-9461-9473f11008e0" />


### 🖱️ Click the Image Above

<p align="center">

<a href="#-project-workflow">
🔄 <b>PROJECT WORKFLOW</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-data-cleaning">
🧹 <b>DATA CLEANING</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-passfail-analysis">
🎯 <b>PASS/FAIL ANALYSIS</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-department-wise-analysis">
🏢 <b>DEPARTMENT ANALYSIS</b>
</a>

</p>

<p align="center">

<a href="#-course-wise-analysis">
📚 <b>COURSE ANALYSIS</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-monthly-average-score">
📅 <b>MONTHLY SCORE</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-data-visualization">
📈 <b>VISUALIZATION</b>
</a>
&nbsp;&nbsp; ➜ &nbsp;&nbsp;

<a href="#-output-files">
💾 <b>OUTPUT FILES</b>
</a>

</p>


## 🏷️ Skills Badges

<p align="center">

![Python](https://img.shields.io/badge/Python-3.13-blue?style=for-the-badge\&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-purple?style=for-the-badge\&logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-blue?style=for-the-badge\&logo=numpy)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Data%20Visualization-orange?style=for-the-badge\&logo=matplotlib)
![SQL](https://img.shields.io/badge/SQL-Data%20Analysis-red?style=for-the-badge\&logo=mysql)
![Excel](https://img.shields.io/badge/Excel-Data%20Analysis-green?style=for-the-badge\&logo=microsoft-excel)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge\&logo=jupyter)

</p>


---
## 📌 Project Overview

🎓 **Student Performance Analysis using Python**

This project focuses on analyzing **student assessment and course performance data** using Python. 📊

### 🔍 What This Project Does

* 📂 **Loads** assessment and course datasets
* 🧹 **Cleans** and prepares the data
* 🔗 **Merges** multiple datasets using `course_id`
* 🎯 **Identifies** Pass/Fail performance
* 🏢 **Analyzes** department-wise performance
* 📚 **Analyzes** course-wise performance
* 📅 **Calculates** monthly average scores
* 📈 **Visualizes** performance using Matplotlib
* 💾 **Exports** cleaned data and analysis results



### 🎯 Project Goal

The main goal of this project is to transform **raw student performance data** into meaningful and actionable insights. 📊

### 🔹 Step 1: Understand Student Performance 📚

Analyze student scores and performance across different courses.

### 🔹 Step 2: Analyze Department Performance 🏢

Compare student performance across different departments.

### 🔹 Step 3: Track Monthly Performance 📅

Calculate and analyze the average student score for each month.

### 🔹 Step 4: Identify Pass/Fail Performance 🎯

Classify assessment results into **Pass** and **Fail** based on the defined score threshold.

### 🔹 Step 5: Create Data Visualizations 📈

Represent important findings using clear and easy-to-understand charts.

### 🔹 Step 6: Generate Analysis Reports 📋

Export cleaned datasets and summary results for further analysis and reporting.

### 💡 Overall Goal

Transform **raw data → cleaned data → analysis → visualization → meaningful insights**. 🚀



### 🎯 Main Objectives

* 📂 **Load assessment and course datasets**
* 🔍 **Check and convert data types**
* 🧹 **Remove duplicate records**
* 🔗 **Merge assessment data with course information**
* 🎯 **Create a `pass_flag` column**
* 🏢 **Calculate department-wise performance**
* 📚 **Calculate course-wise performance**
* 📅 **Calculate monthly average scores**
* 📈 **Create a monthly performance chart**
* 💾 **Export cleaned and summary datasets**

  

### 🚀 Project Outcome

The project transforms **raw student performance data** into **clean, structured, analyzed, and visualized information**. 📊

* 🧹 **Clean Data** — Remove duplicates and prepare reliable data.
* 🔗 **Structured Data** — Combine assessment and course information.
* 📊 **Performance Analysis** — Understand student performance across courses and departments.
* 📅 **Trend Analysis** — Analyze monthly average scores.
* 🎯 **Pass/Fail Insights** — Identify assessment outcomes using `pass_flag`.
* 📈 **Data Visualization** — Present important findings through clear charts.
* 💾 **Useful Reports** — Generate cleaned datasets and summary outputs.

### 💡 Final Result

**Raw Data → Clean Data → Analysis → Visualization → Insights** 🚀📊


---

## 🛠️ Technologies Used

| 🧰 Technology           | 🎯 Purpose                         |
| ----------------------- | ---------------------------------- |
| 🐍 **Python 3.13**      | 💻 Programming & Data Analysis     |
| 🐼 **Pandas**           | 🧹 Data Cleaning & Data Analysis   |
| 🔢 **NumPy**            | 🧮 Numerical Data Processing       |
| 📊 **Matplotlib**       | 📈 Data Visualization              |
| 📁 **CSV**              | 💾 Dataset Storage & Data Handling |
| 📓 **Jupyter Notebook** | 🧪 Analysis & Development          |

---

### 💡 Technology Highlights

* 🐍 **Python** → Core programming language
* 🐼 **Pandas** → Data manipulation and analysis
* 🔢 **NumPy** → Numerical calculations
* 📊 **Matplotlib** → Charts and visualizations
* 📁 **CSV** → Dataset input and output
* 📓 **Jupyter Notebook** → Interactive analysis environment

## 📂 Dataset

The project uses **two CSV datasets** for student performance analysis. 📊

### 📝 `assessments.csv`

Contains **student assessment and performance-related information**:

* 🎯 `score` — Student assessment score
* 📊 `attendance_pct` — Student attendance percentage
* 🔗 `course_id` — Unique course identifier
* 📅 `month` — Assessment month
* 📋 Assessment-related information

### 📚 `courses.csv`

Contains **course and department-related information**:

* 🔗 `course_id` — Unique course identifier
* 📖 `course` — Course name
* 🏢 `department` — Department associated with the course

### 🔗 Dataset Relationship

The two datasets are connected using the **`course_id`** column, which allows assessment performance to be analyzed along with course and department information. 🔍📈

---

## 🔄 Project Workflow

```text
📂 Load CSV Files
       ↓
🔍 Check Data Types
       ↓
🧹 Clean & Remove Duplicates
       ↓
🔗 Merge Assessment + Course Data
       ↓
🎯 Create Pass/Fail Flag
       ↓
🏢 Department-wise Analysis
       ↓
📚 Course-wise Analysis
       ↓
📅 Monthly Average Score
       ↓
📈 Data Visualization
       ↓
💾 Export Analysis Results
```

### 🎬 Project Preview

<p align="center">
  <img src="outputs/python_analysis.gif" alt="Python Data Analysis Preview" width="800">
</p>

---

## 🧹 Data Cleaning

The project performs important **data cleaning and preparation** before analysis. 🛠️

### 🔢 Convert Numeric Columns

The `score` and `attendance_pct` columns are converted into numeric data types.

```python
assessments["score"] = pd.to_numeric(assessments["score"])

assessments["attendance_pct"] = pd.to_numeric(
    assessments["attendance_pct"]
)
```

### 🗑️ Remove Duplicate Rows

Duplicate records are removed to maintain clean and reliable data.

```python
assessments = assessments.drop_duplicates()
```

### 🔗 Merge Datasets

Assessment and course datasets are merged using `course_id`.

```python
merged = assessments.merge(
    courses,
    on="course_id",
    how="left"
)
```

---

## 🎯 Pass/Fail Analysis

A `pass_flag` column is created using **50 as the passing score threshold**.

```python
merged["pass_flag"] = (
    merged["score"] >= 50
).astype(int)
```

### 📌 Pass/Fail Meaning

| Value | Result |
| ----- | ------ |
| ✅ `1` | Pass   |
| ❌ `0` | Fail   |

---

## 📊 Department-wise Analysis

The project analyzes student performance at the **department level**. 🏢

### 📌 Analysis Includes

* 👥 Total assessments
* ✅ Number of passing assessments
* 📈 Pass rate percentage

```python
department_summary = (
    merged.groupby("department")
    .agg(
        total_assessments=("pass_flag", "count"),
        passing_count=("pass_flag", "sum")
    )
    .reset_index()
)
```

### 📈 Pass Rate Calculation

```python
department_summary["pass_rate_%"] = (
    department_summary["passing_count"]
    / department_summary["total_assessments"]
    * 100
)
```

---

## 📚 Course-wise Analysis

The project creates a **course-wise performance summary** to understand student assessment performance across different courses. 📖📊

---

## 📅 Monthly Average Score

The months are arranged in the required order:

```python
month_order = ["Jan", "Feb", "Mar"]
```

The monthly average score is calculated using:

```python
monthly_avg = (
    merged.groupby("month", observed=False)["score"]
    .mean()
    .reindex(month_order)
)
```

This helps identify **monthly performance patterns and trends**. 📈

---

## 📈 Data Visualization

A **Monthly Average Score** bar chart is created using Matplotlib. 📊

```python
plt.figure(figsize=(8, 5), facecolor="lightblue")

monthly_avg.plot(kind="bar")

plt.title("Monthly Average Score")
plt.xlabel("Month")
plt.ylabel("Average Score")
plt.xticks(rotation=0)

plt.tight_layout()
```

### 🖼️ Generated Chart

<img width="790" height="490" alt="image" src="https://github.com/user-attachments/assets/a8d78758-5486-4f2a-bd88-f6069c0ba00e" />

### 💾 Chart Location

```text
outputs/python_chart.png
```

---

## 📁 Output Files

The analysis generates the following output files: 📦

```text
outputs/
│
├── 🧹 clean_data.csv
├── 📊 python_summary.csv
└── 📈 python_chart.png
```

### 🧹 `clean_data.csv`

Contains the **cleaned and merged dataset**.

### 📊 `python_summary.csv`

Contains the **analysis summary results**.

### 📈 `python_chart.png`

Contains the **Monthly Average Score visualization**.

---

## 📂 Project Structure

```text
Python/
│
├── 📓 pythonpro.ipynb
├── 📖 README.md
│
├── 📄 assessments.csv
├── 📄 courses.csv
│
└── 📁 outputs/
    ├── 🧹 clean_data.csv
    ├── 📊 python_summary.csv
    ├── 📈 python_chart.png
    └── 🎬 python_analysis.gif
```

---

## ▶️ How to Run

### 📦 Step 1 — Install Required Libraries

```bash
pip install pandas matplotlib
```

### 💻 Step 2 — Open Jupyter Notebook

```bash
jupyter notebook
```

### 📓 Step 3 — Open the Notebook

```text
pythonpro.ipynb
```

### ▶️ Step 4 — Run All Cells

Run all notebook cells from **top to bottom**.

The cleaned data, summary results, chart, and other outputs will be generated automatically. 🚀

---

## 💡 Key Skills Demonstrated

* 🐍 Python Programming
* 🐼 Pandas
* 🧹 Data Cleaning
* 🔢 Data Type Conversion
* 🗑️ Duplicate Removal
* 🔗 DataFrame Merge
* 📊 `groupby()`
* 🧮 Aggregation
* 🎯 Pass/Fail Analysis
* 📈 Percentage Calculation
* 📅 Categorical Ordering
* 📊 Matplotlib
* 📉 Bar Chart Visualization
* 💾 CSV Export

---

## 🎓 Interview Explanation

### 💬 Project: Student Performance Analysis using Python

> "I created a Student Performance Analysis project using Python and Pandas. I loaded assessment and course datasets, cleaned the data, removed duplicate records, and merged both datasets using `course_id`. Then I created a pass/fail flag based on the score, performed department-wise and course-wise analysis, calculated monthly average scores, and created a Matplotlib bar chart. Finally, I exported the cleaned data and summary results into CSV files."

---

## 👨‍💻 Author

### **Rahul Zala**

**Skills:** 🐍 Python • 🗄️ SQL • 📊 Excel • 📈 Power BI • 📊 Data Analysis

---

## ⭐ Project Support

If you find this project useful, please consider giving the repository a **⭐ Star** on GitHub.

**Thank you for visiting this project!** 🙌
