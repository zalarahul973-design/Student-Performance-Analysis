
<h1 align="center">🚀 Student Performance Analysis – Python</h1>

<p align="center">
  
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

This project performs **Student Performance Analysis using Python**.

The project uses assessment and course datasets to clean, merge, analyze, and visualize student performance data.

### 🎯 Main Objectives

* Load assessment and course datasets
* Check and convert data types
* Remove duplicate records
* Merge assessment data with course information
* Create a `pass_flag` column
* Calculate department-wise performance
* Calculate course-wise performance
* Calculate monthly average scores
* Create a monthly performance chart
* Export cleaned and summary datasets

---

## 🛠️ Technologies Used

| Technology          | Purpose                  |
| ------------------- | ------------------------ |
| 🐍 Python           | Programming & Analysis   |
| 🐼 Pandas           | Data Cleaning & Analysis |
| 📊 Matplotlib       | Data Visualization       |
| 📁 CSV              | Dataset Storage          |
| 📓 Jupyter Notebook | Development              |

---

## 📂 Dataset

The project uses two CSV files:

### `ass essments.csv`

Contains assessment-related information such as:

* `score`
* `attendance_pct`
* `course_id`
* `month`
* Assessment information

### `courses.csv`

Contains course information such as:

* `course_id`
* `course`
* `department`

---

## 🔄 Project Workflow

```text
📂 Load CSV Files
       ↓
🔍 Check Data Types
       ↓
🧹 Remove Duplicate Records
       ↓
🔗 Merge Assessment + Course Data
       ↓
🎯 Create Pass/Fail Flag
       ↓
📊 Department-wise Analysis
       ↓
📚 Course-wise Analysis
       ↓
📅 Monthly Average Score
       ↓
📈 Create Visualization
       ↓
💾 Export Results
```

---

## 🧹 Data Cleaning

The project performs the following cleaning steps.

### 1. Convert Numeric Columns

The `score` and `attendance_pct` columns are converted into numeric data types.

```python
assessments["score"] = pd.to_numeric(assessments["score"])

assessments["attendance_pct"] = pd.to_numeric(
    assessments["attendance_pct"]
)
```

### 2. Remove Duplicate Rows

```python
assessments = assessments.drop_duplicates()
```

### 3. Merge Datasets

The assessment and course datasets are merged using `course_id`.

```python
merged = assessments.merge(
    courses,
    on="course_id",
    how="left"
)
```

---

## 🎯 Pass/Fail Analysis

A `pass_flag` column is created using a score of **50** as the passing threshold.

```python
merged["pass_flag"] = (
    merged["score"] >= 50
).astype(int)
```

### Meaning

```text
1 → Pass
0 → Fail
```

---

## 📊 Department-wise Analysis

The project calculates:

* Total assessments
* Number of passing assessments
* Pass rate percentage

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

### Pass Rate Calculation

```python
department_summary["pass_rate_%"] = (
    department_summary["passing_count"]
    / department_summary["total_assessments"]
    * 100
)
```

---

## 📚 Course-wise Analysis

The project also creates a **course-wise performance summary** to analyze student assessment performance across different courses.

---

## 📅 Monthly Average Score

The months are ordered as:

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

---

## 📈 Data Visualization

A bar chart is created to visualize the **Monthly Average Score**.

```python
plt.figure(figsize=(8, 5), facecolor="lightblue")

monthly_avg.plot(kind="bar")

plt.title("Monthly Average Score")
plt.xlabel("Month")
plt.ylabel("Average Score")
plt.xticks(rotation=0)

plt.tight_layout()
```

The chart is saved as:

```text
outputs/python_chart.png
```

---

## 📁 Output Files

After running the notebook, the following files are generated:

```text
outputs/
│
├── clean_data.csv
├── python_summary.csv
└── python_chart.png
```

### `clean_data.csv`

Contains the cleaned and merged dataset.

### `python_summary.csv`

Contains the generated summary information.

### `python_chart.png`

Contains the monthly average score visualization.

---

## 📂 Project Structure

```text
Python/
│
├── pythonpro.ipynb
├── README.md
│
├── ass essments.csv
├── courses.csv
│
└── outputs/
    ├── clean_data.csv
    ├── python_summary.csv
    └── python_chart.png
```

---

## ▶️ How to Run

### Step 1 – Install Required Libraries

```bash
pip install pandas matplotlib
```

### Step 2 – Open Jupyter Notebook

```bash
jupyter notebook
```

### Step 3 – Open the Notebook

```text
pythonpro.ipynb
```

### Step 4 – Run All Cells

Run the notebook cells from top to bottom.

The analysis results and output files will be generated automatically.

---

## 💡 Key Skills Demonstrated

* Python Programming
* Pandas
* Data Cleaning
* Data Type Conversion
* Duplicate Removal
* DataFrame Merge
* `groupby()`
* Aggregation
* Pass/Fail Analysis
* Percentage Calculation
* Categorical Ordering
* Matplotlib
* Bar Chart Visualization
* CSV Export

---

## 🎓 Interview Explanation

**Project:** Student Performance Analysis using Python

> "I created a Student Performance Analysis project using Python and Pandas. I loaded assessment and course datasets, cleaned the data, removed duplicate records, and merged both datasets using `course_id`. Then I created a pass/fail flag based on the score, performed department-wise and course-wise analysis, calculated monthly average scores, and created a Matplotlib bar chart. Finally, I exported the cleaned data and summary results into CSV files."

---

## 👨‍💻 Author

**Rahul Zala**

**Skills:** Python • SQL • Excel • Power BI • Data Analysis

---

⭐ If you find this project useful, please give the repository a Star.
