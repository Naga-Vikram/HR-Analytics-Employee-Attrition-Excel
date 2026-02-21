# 📊 HR Analytics – Employee Attrition Dashboard (Excel)

## 🎯 Why This Analysis
Employee attrition is one of the most costly and least visible challenges faced by organizations. High turnover leads to increased hiring costs, loss of institutional knowledge, reduced team productivity, and long-term impacts on employee morale.

This analysis was undertaken to **move beyond surface-level attrition numbers** and identify the **underlying drivers** influencing employee departures—such as department, job role, and overtime patterns. The goal was to translate raw HR data into **actionable insights** that HR teams and business leaders can use to improve retention strategies.

By building this project in Excel, the analysis also demonstrates how a widely used business tool can be leveraged to perform **structured, scalable, and decision-focused analytics**, similar to real-world HR reporting environments.

The emphasis is not just on visualization, but on **business-oriented analysis**, metric integrity, and professional dashboard design.

---

## 📁 Dashboard File
- **File Name:** `HR_Attrition_Dashboard.xlsx`
- **Tool Used:** Microsoft Excel
- **Dashboard Type:** Interactive, slicer-driven
- **Target Audience:** HR Managers, Business Analysts, Decision Makers

The dashboard enables dynamic exploration of attrition trends while **preserving stable executive KPIs**.

---

## 🛠️ Excel Skills Used
- 🔄 Power Query (data ingestion & transformation)
- 🧠 Power Pivot (data modeling & DAX measures)
- 📊 Pivot Tables & Pivot Charts
- 🧮 DAX measures for KPI computation
- 🔗 GETPIVOTDATA for stable KPI linking
- 🎛️ Slicers with controlled report connections
- 🔒 Sheet protection with unlocked slicers
- 🎨 Dashboard layout & visual hierarchy design

---

## 🗂️ Dataset
- **Original Source:** [IBM HR Analytics Employee Attrition dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
- **Database Storage:** PostgreSQL database hosted on Supabase
- **Access Method:** Data extracted from Supabase and ingested into Excel using Power Query
- **Records:** 1,470 employees

---

## 🔄 Data Pipeline
- Dataset staged in a **Supabase-hosted PostgreSQL database**
- Data extracted and exported for analytics
- Ingested into Excel using **Power Query**
- Modeled using **Power Pivot** for KPI computation

This pipeline mirrors **real-world analytics workflows**, making the project industry-relevant.

---

## 🏗️ Dashboard Build
The dashboard was developed using a **layered architecture**:

1. **📥 Data Layer**
   - Data loaded using Power Query
   - Cleaned without artificial filtering to maintain business realism

2. **🧠 Model Layer**
   - Data stored in Excel’s Data Model
   - KPIs calculated using DAX measures in Power Pivot

3. **📈 Analysis Layer**
   - Pivot tables for department, job role, and overtime analysis
   - Slicers applied only to analysis pivots

4. **🖥️ Presentation Layer**
   - Executive KPIs isolated from slicers
   - Interactive charts and filters
   - Protected dashboard structure

This approach ensures **accuracy, scalability, and professional usability**.

---

## 📊 Charts

### 1️⃣ Attrition Rate by Department

<img width="707" height="335" alt="Attrition by Department" src="https://github.com/user-attachments/assets/85a1cf5f-8c59-4f1a-bb3a-9a2ce4b60c09" />

- **Excel Feature:** Pivot Chart (Column Chart)
- **Design Choice:** Vertical bars for easy department comparison
- **Data Organization:** Department as category, Attrition Rate as measure
- **🔍Insight:**  
  Sales shows the highest attrition rate, indicating higher retention risk compared to R&D.

---

### 2️⃣ Overtime vs Attrition

<img width="706" height="372" alt="Overtime vs Attrition" src="https://github.com/user-attachments/assets/542a650b-2bc1-443e-9c29-cf199ab38429" />

- **Excel Feature:** Pivot Chart (Column Chart)
- **Design Choice:** Side-by-side comparison for Yes vs No
- **Data Organization:** Overtime status as category, Attrition Rate as measure
- **🔍Insight:**  
  Employees working overtime are nearly **3× more likely to leave**, making overtime the strongest attrition driver.

---

## 🧮 Formulas and Functions

### DAX Measures (Power Pivot)

**Purpose:**  
Ensure KPI calculations remain **consistent, context-aware, and scalable** across all PivotTables and dashboard visuals.

**Key Measures Used:**

#### Total Employees
```DAX
Total Employees :=
COUNT(HR_Attrition_Final_Data[employee_id])
```  
#### Attrition Count
```DAX
Attrition Count :=
CALCULATE(
    COUNT(HR_Attrition_Final_Data[employee_id]),
    HR_Attrition_Final_Data[attrition] = "Yes"
)
```
#### Attrition Rate
```DAX
Attrition Rate :=
DIVIDE(
    [Attrition Count],
    [Total Employees]
)
```
#### Overtime Attrition Rate
```DAX
Overtime Attrition Rate :=
DIVIDE(
    CALCULATE(
        COUNT(HR_Attrition_Final_Data[employee_id]),
        HR_Attrition_Final_Data[attrition] = "Yes",
        HR_Attrition_Final_Data[overtime] = "Yes"
    ),
    CALCULATE(
        COUNT(HR_Attrition_Final_Data[employee_id]),
        HR_Attrition_Final_Data[overtime] = "Yes"
    )
)
```

These measures ensure calculations are **context-aware** and reusable across pivots.

---


## ✅Conclusion
This project demonstrates how Excel can be used beyond spreadsheets — as a **professional analytics and reporting platform**.

It showcases:
- 📌 Business-driven problem solving
- 📐 SQL-style metric thinking applied in Excel
- 🔄 Proper separation of KPIs and analysis
- 🎛️ Interactive yet controlled dashboard design


---

