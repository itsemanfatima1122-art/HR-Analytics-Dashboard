# 👥 HR Analytics Dashboard

An interactive and visually powerful **Power BI Dashboard** built to analyze employee attrition, uncover workforce trends, and help organizations make data-driven HR decisions — from salary patterns to job satisfaction scores.

---

## 📌 Short Description / Purpose

This dashboard provides a **comprehensive view of HR data**, enabling organizations to monitor employee attrition, identify at-risk groups, and understand key factors driving workforce turnover. Through interactive visuals and smart KPIs, it transforms raw HR data into actionable business insights.

---

## 🛠️ Tech Stack

The dashboard was built using the following tools and technologies:

| Tool | Purpose |
|------|---------|
| 📊 **Power BI Desktop** | Main platform for building interactive dashboards |
| 📂 **Power Query Editor** | Data cleaning, transformation & null value handling |
| 🧠 **DAX (Data Analysis Expressions)** | Calculated columns & custom measures (e.g., Attrition Rate) |
| 🔗 **Data Modeling** | Relationships between data fields for cross-filtering |
| 📁 **File Formats** | `.pbix` (development), `.png` (dashboard preview) |

---

## 📊 Data Source

This project uses a sample **HR Analytics dataset** containing **38 columns** including:

- Employee demographics (Age, Gender, Age Group)
- Attrition status (Yes / No)
- Department & Job Role
- Education Field & Education Level
- Monthly Income & Salary Slab
- Job Satisfaction Score (1–4)
- Years at Company
- Business Travel frequency
- And more...

> 📁 The dataset is used for **learning and data visualization purposes** only.

---

## 🚀 Features / Highlights

### 🔹 Business Problem

Organizations face high costs due to employee turnover. Key unanswered questions include:

- Which **age groups** are most likely to leave?
- Which **departments and job roles** have the highest attrition?
- Does **salary** play a major role in employees quitting?
- How does **job satisfaction** correlate with attrition?
- At what **tenure milestone** do employees typically leave?

---

### 🔹 Goal of the Dashboard

To build an interactive HR dashboard that:

- Tracks **key attrition metrics** at a glance
- Identifies **patterns** in employee exits by age, salary, role & tenure
- Helps HR teams take **proactive retention decisions**
- Enables **department-level filtering** for focused analysis

---

## 🔍 Walkthrough of Key Visuals

### 📌 KPI Cards (Top Section)

| KPI | Value |
|-----|-------|
| 👨‍💼 Total Employees | 1,470 |
| 🚪 Total Attrition Count | 237 |
| 📉 Attrition Rate | 16.1% |
| 🎂 Average Employee Age | 37 years |
| 💰 Average Monthly Salary | 6.5K |
| 🏢 Avg. Years at Company | 7.0 years |

---

### 📈 Attrition by Education Field

> Donut chart showing which education backgrounds have the most attrition.

- Life Sciences and Medical fields lead in attrition count due to higher employee volume in those fields.

### 👥 Attrition by Age Group

> Bar chart revealing which age brackets are most likely to leave.

- The **26–35 age group** shows the highest attrition — a critical finding for retention strategy.

### 💳 Attrition by Salary Slab

> Horizontal bar chart breaking down attrition by income bracket.

- Employees earning **up to 5K/month** account for the majority of exits (163 out of 237).
- This confirms **low salary as a primary attrition driver**.

### 🏢 Attrition by Years at Company

> Area chart showing attrition patterns over employee tenure.

- **Year 1** sees the highest attrition (59 employees) — onboarding & culture fit issues likely.
- Spikes also occur around **Year 5** and **Year 10** — milestone-driven turnover.

### 😊 Job Satisfaction by Job Role (Matrix Table)

> Matrix showing job roles vs. satisfaction scores (1–4) vs. attrition count.

- **Lab Technicians** with low satisfaction scores (1) show high attrition.
- Helps HR prioritize which roles need immediate engagement intervention.

### 👤 Attrition by Job Role (Top 4)

> Horizontal bar chart of the top 4 roles with highest attrition.

- Lab Technician, Sales Executive, Research Scientist, Sales Representative top the list.

### ⚧️ Gender Distribution (TreeMap)

> TreeMap showing Male vs. Female employee distribution.

### 🎛️ Department Filter (Slicer)

> Tile-style slicer to filter the entire dashboard by:

- Human Resources
- Research & Development
- Sales

---

## 💡 Business Impact & Insights

| Insight | Action |
|---------|--------|
| 📉 16.1% attrition rate | Benchmark and set reduction targets |
| 💸 Low salary = high turnover | Review compensation for the <5K salary band |
| 🧑 Year 1 exits are highest | Improve onboarding & early engagement programs |
| 🔬 Lab Technicians most at risk | Conduct targeted satisfaction surveys |
| 🎓 Life Science grads leave most | Review role-fit for this education segment |
| 📅 Year 5 & 10 tenure spikes | Create milestone-based retention incentives |

---

## 🧹 Data Cleaning Steps (Power Query)

- ✅ Removed **null values** using Sort + Remove Top Rows method
- ✅ Removed **duplicate records** across all 38 columns
- ✅ Fixed **spelling inconsistencies** (e.g., `Travel_Rarely` vs `TravelRarely`) using Replace Values
- ✅ Auto-detected **data types** using Transform → Detect Data Types
- ✅ Created **Attrition Count** column (Yes = 1, No = 0) using Conditional Column
- ✅ Created **Attrition Rate** DAX measure:

```DAX
Attrition Rate =
SUM('HR'[Attrition Count]) / SUM('HR'[Employee Count])
