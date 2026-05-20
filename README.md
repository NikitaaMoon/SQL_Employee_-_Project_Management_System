<h1 align="center"> Employee & Project Management System</h1>

<p align="center">
  Advanced SQL JOINs Project | SQL Server
</p>

<p align="center">
  <a href="https://github.com">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=18&duration=3000&pause=800&color=4F8EF7&center=true&vCenter=true&width=700&height=60&lines=8+JOIN+Types+%E2%80%A2+27+Stored+Procedures+%E2%80%A2+12+Tables;INNER+%7C+LEFT+%7C+RIGHT+%7C+FULL+OUTER+%7C+SELF+%7C+CROSS+%7C+ANTI" alt="Typing SVG" />
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white" />
  <img src="https://img.shields.io/badge/T--SQL-4479A1?style=for-the-badge&logo=databricks&logoColor=white" />
  <img src="https://img.shields.io/badge/Status-Complete-38D9A9?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Procedures-27-F6C90E?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Tables-12-FF6B6B?style=for-the-badge" />
</p>

---

## 📋 Project Overview

> A production-grade SQL Server project that demonstrates **every JOIN type** through real-world HR, payroll, and project-management scenarios — bridging the gap between textbook theory and enterprise-level SQL.

| Property | Details |
|---|---|
| 🗄️ **Database** | `AdvancedJoinDB` |
| 🖥️ **Platform** | Microsoft SQL Server |
| 🏢 **Domain** | Enterprise HR & Project Management |
| 🏗️ **Architecture** | 12 tables · 27+ stored procedures |
| 🎯 **Focus** | All JOIN types in real business patterns |
| ⚙️ **Complexity** | Multi-table · Self-referencing · Anti-joins |

---

## 🎯 Problem Solved

Most SQL JOIN tutorials stop at `INNER JOIN` with two tables. This project solves that gap by implementing **every JOIN variant** — including rare Anti-Joins and Self-Joins — inside a realistic Enterprise HR schema.

Each stored procedure models a genuine business query:

- 🔍 Detecting unassigned employees
- 💰 Comparing salaries across teams
- 📊 Skill-gap analysis before project start
- 🗂️ Management hierarchy traversal
- 📅 Payroll and attendance auditing

---

## 🔗 JOIN Types Covered

<div align="center">

| JOIN Type | Procedures | Real-World Use Case |
|---|---|---|
| `INNER JOIN` | 3 | Employee–Department–Manager matching |
| `LEFT JOIN` | 4 | Employees with or without projects |
| `RIGHT JOIN` | 2 | Projects with or without staff |
| `FULL OUTER JOIN` | 2 | Attendance & review gap detection |
| `SELF JOIN` | 4 | Manager hierarchy & salary comparison |
| `CROSS JOIN` | 2 | Employee × Skill matrix planning |
| `LEFT ANTI JOIN` | 5 | Unassigned / under-reviewed employees |
| `RIGHT ANTI JOIN` | 2 | Orphaned projects & teamless managers |

</div>

---

## 🛠️ Tools & Technologies

<p align="center">
  <img src="https://img.shields.io/badge/SQL%20Server%202019+-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white" />
  <img src="https://img.shields.io/badge/SSMS-0078D4?style=flat-square&logo=microsoft&logoColor=white" />
  <img src="https://img.shields.io/badge/Azure%20Data%20Studio-0089D6?style=flat-square&logo=microsoftazure&logoColor=white" />
  <img src="https://img.shields.io/badge/T--SQL-4479A1?style=flat-square&logo=databricks&logoColor=white" />
</p>

```
✔ Stored Procedures           ✔ IDENTITY & FK Chains
✔ COALESCE / NULLIF           ✔ CASE Expressions
✔ Aggregate Functions         ✔ GETDATE / DATEPART
✔ DECIMAL / NVARCHAR types    ✔ Self-Referential Relationships
✔ NOT EXISTS (Anti-Joins)     ✔ Multi-table Complex JOINs
```

---

## 📊 Key Results

<div align="center">

| Metric | Value |
|---|---|
| 🗂️ Relational Tables | **12** |
| ⚙️ Stored Procedures | **27** |
| 🔗 JOIN Variants | **8** |
| 🏢 Companies / Departments | **3 / 6** |
| 📝 Parameterised Queries | **100%** |
| 🔄 Many-to-Many Bridges | **3** (Skills · Projects · Training) |

</div>

---

## 💡 Technical Skills Demonstrated

```sql
-- Self-referencing hierarchy (SELF JOIN)
CREATE TABLE Employees (
  EmpID     INT PRIMARY KEY IDENTITY,
  ManagerID INT REFERENCES Employees(EmpID),   -- points to itself!
  DeptID    INT REFERENCES Departments(DeptID),
  Salary    DECIMAL(10,2),
  Status    NVARCHAR(20)
);

-- Complex multi-table JOIN — Employee Performance Dashboard
SELECT
    e.FirstName + ' ' + e.LastName  AS EmployeeName,
    COUNT(DISTINCT pa.ProjectID)     AS ProjectsAssigned,
    COUNT(DISTINCT es.SkillID)       AS SkillCount,
    AVG(pr.PerformanceScore)         AS AvgScore,
    CASE
        WHEN AVG(pr.PerformanceScore) >= 4.5 THEN 'Excellent'
        WHEN AVG(pr.PerformanceScore) >= 4.0 THEN 'Very Good'
        ELSE 'Needs Improvement'
    END                              AS Rating
FROM       Employees          e
LEFT JOIN  ProjectAssignments pa ON e.EmpID = pa.EmpID
LEFT JOIN  EmployeeSkills     es ON e.EmpID = es.EmpID
LEFT JOIN  PerformanceReviews pr ON e.EmpID = pr.EmpID
LEFT JOIN  EmployeeTraining   et ON e.EmpID = et.EmpID
WHERE e.Status = 'Active'
GROUP BY e.EmpID, e.FirstName, e.LastName
ORDER BY AvgScore DESC;
```

**Skills at a Glance:**

| Skill | Level |
|---|---|
| Advanced JOIN Mastery | `████████████████████` 95% |
| Schema Design & FK Architecture | `███████████████████░` 90% |
| Stored Procedure Development | `████████████████████` 92% |
| Analytical SQL (Aggregates, CASE) | `██████████████████░░` 88% |
| NULL Handling & Anti-Join Patterns | `█████████████████░░░` 85% |
| Self-Referential Modelling | `████████████████░░░░` 80% |

---

## 🚀 Business Impact

| # | Impact Area | Description |
|---|---|---|
| 👥 | **Workforce Visibility** | Full manager–subordinate hierarchy and cross-department colleague mapping in a single procedure call |
| 📊 | **Resource Planning** | Project capacity analysis flags over- and under-utilised teams, supporting budget decisions |
| 🔍 | **Skill Gap Detection** | CROSS JOIN + LEFT ANTI JOIN reveals missing expert coverage *before* projects begin |
| 💰 | **Payroll & Compensation** | Salary comparison via Self-Join and attendance audits surface payroll anomalies |
| 🏆 | **Performance Intelligence** | Multi-table JOINs produce a single composite employee score across all dimensions |
| 🔄 | **Reusable Patterns** | Every procedure is a production-ready template adaptable to any ERP or HRMS |

---

## 🗄️ Database Schema

```
AdvancedJoinDB
│
├── Companies          (CompanyID, CompanyName, Industry, Country)
│   └── Departments    (DeptID, CompanyID → FK, DeptHead, Budget)
│       ├── Employees  (EmpID, DeptID → FK, ManagerID → SELF FK)
│       │   ├── EmployeeSkills      (EmpID → FK, SkillID → FK)
│       │   ├── ProjectAssignments  (EmpID → FK, ProjectID → FK)
│       │   ├── PerformanceReviews  (EmpID → FK, ReviewerID → SELF FK)
│       │   ├── Attendance          (EmpID → FK, Date, Status)
│       │   ├── Salaries            (EmpID → FK, Month, Bonus)
│       │   ├── EmployeeTraining    (EmpID → FK, CourseID → FK)
│       │   └── LeaveRequests       (EmpID → FK, ApprovedBy → SELF FK)
│       └── Projects   (ProjectID, DeptID → FK, ProjectManager → FK)
│
├── Skills             (SkillID, SkillName, Category, DifficultyLevel)
└── TrainingCourses    (CourseID, CourseName, DurationDays, Cost)
```

---

## ▶️ How to Run

```sql
-- 1. Open SSMS or Azure Data Studio
-- 2. Run the full script to create the database, tables & procedures

-- 3. Execute any stored procedure individually
EXEC sp_InnerJoin_EmployeeDepartmentManager;
EXEC sp_LeftJoin_EmployeesWithProjects;
EXEC sp_SelfJoin_ManagerSubordinate;
EXEC sp_CrossJoin_EmployeeSkillMatrix;
EXEC sp_LeftAntiJoin_UnassignedEmployees;
EXEC sp_ComplexJoin_EmployeePerformanceAnalysis;

-- 4. Or run all at once — uncomment the EXEC block at bottom of script
```

---

## 📁 File Structure

```
📦 Advanced_All_JOINs_Project
 ┣ 📄 Advanced_All_JOINs_Project.sql   ← Main script (tables + procedures)
 ┗ 📄 README.md                        ← This file
```

---

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer" width="100%"/>
</p>

<p align="center">
  ⭐ <strong>Star this repo if it helped you level up your SQL skills!</strong>
</p>
