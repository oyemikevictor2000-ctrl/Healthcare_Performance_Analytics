# 🏥 Healthcare Performance & Executive Analytics Dashboard

---

## 📌 Executive Preview

This end-to-end Healthcare Analytics Solution unifies clinical, operational, and financial data across multi-branch hospital operations in **Nigeria** (covering **Rivers, Lagos, Abuja, and Anambra** states). 

Designed specifically for executive leadership and hospital administrators, the dashboard converts complex, raw healthcare transaction logs into actionable, real-time insights. By tracking financial growth, capacity bottlenecks, patient care outcomes, and satisfaction metrics, this platform equips decision-makers to optimize resource allocation, enhance revenue capture, and improve patient throughput across all operational branches.

### 📊 Key Performance Highlights (At a Glance)
* **Total Hospital Revenue:** ₦47.84M
* **Total Operational Cost:** ₦29.00M
* **Total Net Profit:** ₦18.35M (**38.4%** Overall Profit Margin)
* **Average Revenue Per Patient:** ₦39.87K
* **Revenue Target & Gap:** ₦200.00M Target (**-₦152.16M to -₦187.27M** Regional Variance)
* **Patient Visit Volume:** 1,200 unique tracked patients generating **3,000+ total visits** (2,920 recorded across primary branches)
* **Average Patient Waiting Time:** **45.27 – 46.11 minutes**
* **Average Satisfaction Score:** **3.71 / 5.00**

---

## 💼 Business Problem

Healthcare organizations operating across multiple geographic regions face significant operational and financial management challenges. Prior to this analytical solution, leadership lacked a consolidated, real-time view of network performance, resulting in key pain points:

1. **Unidentified Financial Gaps:** Inability to track real-time variance against the target revenue of ₦200M across individual state branches and operational units.
2. **Resource Allocation Inefficiencies:** Limited clarity on which medical departments generate optimal profit margins versus those operating with inflated costs.
3. **Patient Throughput & Flow Bottlenecks:** Lack of visibility into department-level waiting times, leading to patient dissatisfaction and extended care turnaround times.
4. **Demographic & Diagnostic Blindspots:** Insufficient tracking of patient retention rates (new vs. returning), primary diagnostic trends (e.g., Malaria prevalence), and treatment outcome performance across age groups.

---

## ❓ Business Questions & Answers

### 1. Financial Growth & Revenue Target Variance
* **Business Question:** Why are state branches consistently falling short of the ₦200M revenue target, and which locations generate the highest revenue?
* **How We Answered It:** We modeled revenue targets against actual earnings using DAX variance logic (`Revenue Target - Total Revenue`). The analysis showed that **Rivers State** is the top-performing territory generating **~₦12.7M**, while **Anambra State** is the lowest-performing branch at **₦11.33M**. Branch-level drill-throughs revealed that severe negative variances exist across all facilities (e.g., Port Harcourt at **-₦196.1M** variance), indicating that revenue targets were set higher than existing patient throughput capacity.

### 2. Departmental Profitability & Cost Efficiency
* **Business Question:** Which medical departments act as core profit drivers, and where are operational costs eroding profitability?
* **How We Answered It:** By calculating cost-to-revenue ratios and margin percentages at the department level, we identified **Pediatrics** as the primary profit engine yielding **~₦3.7M** in total profit, followed by **Outpatient (₦3.14M)** and **Emergency (₦2.93M)**. Conversely, **Maternity** generated the lowest profit at **~₦2.8M**, signaling an immediate need for operational cost optimization and service restructuring.

### 3. Operational Throughput & Waiting Time Bottlenecks
* **Business Question:** Which specific departments experience the longest patient waiting times, creating workflow bottlenecks?
* **How We Answered It:** We aggregated patient arrival logs and consult duration metrics across all departments. The data revealed that **Laboratory Test** records the longest delay with an average waiting time of **47.0 minutes**, followed closely by **Pediatrics** and **Pharmacy**. Furthermore, seasonal volume surges in July created systemic bottlenecks across Emergency and Outpatient throughput.

### 4. Patient Demographics, Retention & Outcome Tracking
* **Business Question:** What is the hospital's patient retention rate, what are the primary medical diagnoses, and how effectively are patients recovering?
* **How We Answered It:** By categorizing diagnostic records and visit types, we discovered that **74.08% (889 patients)** are returning patients, while **25.92% (311 patients)** are new. **Malaria (283 patients)** emerged as the most common diagnosis, with **Adults (858 patients)** forming the largest demographic group. On care outcomes, **54.08% (649 patients)** were successfully **Recovered**, **21.92% (263)** were **Admitted**, **12.92% (155)** were **Referred**, and **11.08% (133)** required **Follow-up**.

### 5. Patient Experience vs. Service Satisfaction
* **Business Question:** Do extended waiting times directly lower patient satisfaction scores across care departments and age groups?
* **How We Answered It:** We cross-analyzed satisfaction scores against waiting times by department, branch, and age category. **Pharmacy** achieved the highest satisfaction average at **3.74 / 5.00**, whereas **Maternity** recorded the lowest rating at **3.69 / 5.00**. Across age demographics, **Adults and Children** reported higher satisfaction ratings than **Elderly** patients, highlighting specific areas for geriatric care enhancement.

---

## 🛠️ Tools & Technologies Used

* **Microsoft Excel:** Data structure setup, initial validation, and raw healthcare transaction log formatting.
* **Power Query (ETL):** Automated Extract, Transform, Load (ETL) pipeline execution—handling missing value imputation, type conversions, demographic grouping, conditional column creation, and data cleaning.
* **Power BI Desktop:** Multi-page interactive dashboard development featuring desktop and responsive mobile views, dynamic bookmark navigation, hover tooltips, visual drill-throughs, and conditional formatting.
* **DAX (Data Analysis Expressions):** Custom statistical logic, time intelligence formulas, variance tracking measures, and dynamic text generation.
* **GitHub:** Repository hosting, documentation management, and version control.

---

## 🗃️ Dataset Architecture & Data Dictionary

The project dataset integrates patient admission logs, clinical diagnostic categories, operational wait times, and financial billing records:

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| **Patient_ID** | Text / Key | Unique identification code assigned to each patient. |
| **State** | Text | Geographic state location (*Rivers, Lagos, Abuja, Anambra*). |
| **Branch** | Text | Specific facility location (*Port Harcourt, Trans Amadi, Obio-Akpor, Lekki, Ikeja, Maitama, Wuse, Garki, Onitsha, Awka, Nnewi, Yaba*). |
| **Gender** | Text | Patient gender classification (*Male: 608, Female: 592*). |
| **Age / Age_Grade** | Numeric / Text | Patient age and demographic categorization (*Child, Teenager, Adult, Elderly*). |
| **Department** | Text | Hospital operational unit (*Pediatrics, Outpatient, Emergency, Laboratory, Pharmacy, Maternity*). |
| **Service** | Text | Specific healthcare service delivered (*Pediatric Care, General Consultation, Emergency Care, Laboratory Test, Maternity Care, Pharmacy*). |
| **Diagnosis** | Text | Identified medical condition (*Malaria, Typhoid, Hypertension, Respiratory Infection, Diabetes, etc.*). |
| **Visit_Type / PT Status** | Text | Patient classification (*Returning Patient vs. New / Non-returning Patient*). |
| **Patient_Outcome** | Text | Final patient discharge disposition (*Recovered, Admitted, Referred, Follow-up*). |
| **Waiting_Time_Mins** | Numeric | Elapsed time (in minutes) from patient arrival to medical consultation. |
| **Satisfaction_Score** | Numeric | Rating score provided by the patient on a 1.00 to 5.00 scale. |
| **Revenue / Total Cost** | Currency | Total revenue generated and operational cost incurred per visit transaction. |
| **Visit_Date** | Date | Transaction timestamp used for Month-over-Month (MoM) and historical trend analysis. |

---

## 📐 DAX Data Modeling & Calculated Measures

All custom analytical calculations were centralized into a structured `Measures_Table`:

* **`Achievement %`:** Calculates percentage of revenue target attained across branches.
* **`Average Revenue Per Patient`:** `DIVIDE([Total Revenue], [Total Patients], 0)` $\rightarrow$ **₦39.87K**.
* **`Average Satisfaction`:** `AVERAGE('HealthcareData'[Satisfaction_Score])` $\rightarrow$ **3.71**.
* **`Average Visits per Patient`:** `DIVIDE([Total Visits], [Total Patients], 0)` $\rightarrow$ **2.43**.
* **`Average Waiting Time`:** `AVERAGE('HealthcareData'[Waiting_Time_Mins])` $\rightarrow$ **45.27 mins**.
* **`Busiest Department`:** Evaluates top visit volume dynamically $\rightarrow$ *"The busiest department is Pediatrics with 515 visits."*
* **`Longest Wait Department`:** Evaluates peak queue times dynamically $\rightarrow$ *"The department with the longest wait time is Laboratory with an average waiting time of 47.0 minutes."*
* **`Executive Insight`:** Formats automated executive summaries highlighting target gaps and top/bottom state performers in real-time.
* **`MoM Revenue Growth %`:** Evaluates monthly percentage growth trends in revenue $\rightarrow$ **7.6% MoM Growth**.
* **`Profit Margin %`:** `DIVIDE([Total Profit], [Total Revenue], 0)` $\rightarrow$ **38.4%**.
* **`Previous Month Revenue` & `Previous Year Revenue`:** Time intelligence expressions evaluating historical sales trends.

---

## 📱 Dashboard Architecture & Navigation

The Power BI report is organized into four interactive core pages plus custom mobile layout configurations:

1. **Healthcare Performance Executive Dashboard (Mobile View Optimized):** Executive overview displaying top-level KPIs (`Total Profit`, `Total Revenue`, `Average Revenue Per Patient`, `Satisfaction Score`), state slicers, temporal revenue lines, and departmental volume charts.
2. **Hospital Operations & Efficiency:** Detailed breakdown of busiest/longest-wait departments, outcome donut charts, patient volume trends, and queue bottleneck indicators.
3. **Hospital Financial Performance:** Deep financial drill-down tracking departmental profit margins (e.g., Lagos at 38.9%), MoM growth rates (7.6%), and revenue target variances.
4. **Patient Experience & Insights:** Demographic analysis covering age-grade distributions, gender breakdowns, patient loyalty metrics (74.08% returning rate), and branch-level satisfaction scores.
5. **Drill-Through & Custom Tooltips:** Enables leadership to right-click or tap any branch visual to instantly load pre-filtered detail audit tables.

---

## 💡 Strategic Recommendations for Executive Management

1. **Streamline Laboratory & Emergency Workflows:** Implement digital queue routing and triage optimization in **Laboratory (47.0 min wait time)** and **Emergency** to reduce patient delays during seasonal surges like July.
2. **Expand High-Margin Service Lines:** Allocate additional operational resources, beds, and personnel to **Pediatrics (₦3.7M profit)** and **Outpatient Care (₦3.14M profit)** to maximize high-margin revenue streams.
3. **Optimize Maternity Operations:** Conduct internal operational reviews within **Maternity** to raise patient satisfaction ratings (3.69 / 5.00) and improve service profitability (₦2.8M profit).
4. **Targeted Regional Strategy for Anambra State:** Develop regional outreach and patient acquisition campaigns in **Anambra State** to elevate branch revenue from ₦11.33M closer to top benchmarks established in Rivers State (₦12.7M).
---
---

## 👤 Author & Contact

* **Developer:** Victor Oyemike
* **Role:** Data Analyst / BI Developer
* **Email:** [oyemikevictor2000@gmail.com]

---
*If you find this project helpful or interesting, feel free to leave a 🌟 on the repository!*
