
# Fethi-Atlas-Labs-Employee-Attrition

## Atlas Labs Employee Attrition Analysis

## Introduction

A Tableau Dashboard project developing and showcasing my skills in creating comprehensive analyses and interactive visualizations. This project focuses on employee attrition at Atlas Labs, a fictional company, and investigates the various factors contributing to the reduction in staff numbers. The analysis explores several variables, both independently and in combination, such as age, gender, department, education level, job satisfaction, and travel frequency. The aim is to uncover key insights that help explain attrition trends and inform actionable strategies to improve employee retention and satisfaction.

**Key Question:**  
What are the key factors driving employee attrition at Atlas Labs, and how can we improve retention?

---

## Overview of Key Metrics

### Dashboard Visuals
- **Attrition Trends**  
  ![Attrition Trends Over Time](https://raw.githubusercontent.com/FethiAbdul/Fethi-Atlas-Labs-Employee-Attrition/main/Dashboard%20Images/dashboard_labs_1.png)

- **Additional Analysis**  
  ![Additional Analysis](https://raw.githubusercontent.com/FethiAbdul/Fethi-Atlas-Labs-Employee-Attrition/main/Dashboard%20Images/dashboard_labs_2.png)

- **Insights on Attrition by Factors**  
  ![Insights on Attrition by Factors](https://raw.githubusercontent.com/FethiAbdul/Fethi-Atlas-Labs-Employee-Attrition/main/Dashboard%20Images/dashboard_labs_3.png)

- **Recommendations Overview**  
  ![Recommendations Overview](https://raw.githubusercontent.com/FethiAbdul/Fethi-Atlas-Labs-Employee-Attrition/main/Dashboard%20Images/dashboard_labs_4.png)

### Workforce Summary
- **Total Employees:** 1,468  
- **Current Employees:** 1,233  
- **Past Employees:** 237  
- **Attrition Rate:** 16.1%  

### Departmental Insights
- **Technology Department:** Largest department with 961 employees and an attrition rate of 13.8%.
- **Sales Department:** High attrition, with sales representatives having the highest rate (39.7%).
- **HR Department:** Smaller workforce with lower attrition.

---

## Attrition Trends

### Key Findings:
- The highest attrition rate occurred in **2020 (22.05%)**, followed by **2016 (21.05%)**.
- Employees with **0–1 years of tenure** experience the highest attrition (34.5%).
- Attrition rates have remained stable despite a general decline in hiring from 2012 to 2023.

---

## Demographics and Diversity

### Key Insights:
- **Age Distribution:** Majority of employees are aged **20–29 (59.4%)**.
- **Gender Distribution:** Nearly equal between male and female employees, with **non-binary** employees representing 5.04%.
- **Ethnicity and Salary:**
  - White employees have the highest average salary.
  - Employees from "Mixed or multiple ethnic groups" earn the lowest average salaries.

---

## Calculated Fields in Tableau Analysis

Several calculated fields were created in Tableau to derive key insights and support the analysis:


### 1. Age Group
IF [Age] < 20 THEN "Under 20"
ELSEIF [Age] >= 20 AND [Age] <= 29 THEN "20–29"
ELSEIF [Age] >= 30 AND [Age] <= 39 THEN "30–39"
ELSEIF [Age] >= 40 AND [Age] <= 49 THEN "40–49"
ELSE "Over 50"
END

### 2. Attrition Rate
[Past Employees] / [Total Employees]

### 3. Ranking by Attrition Rate
RANK_PERCENTILE([Attrition Rate])

### 4. Proportional Contribution to Total Attrition
[Attrition Rate] / TOTAL([Attrition Rate])

### 5. Ranking by Current Employees
RANK_PERCENTILE([Current Employees])

### 6. Current Employees
IF [Attrition] = "No" THEN [Employee ID]
ELSE NULL
END

### 7. Past Employees
IF [Attrition] = "Yes" THEN [Employee ID]
ELSE NULL
END

### 8. Total Employees
COUNTD([Employee ID])


# Attrition Analysis

## By Seniority
- Employees in their **first year (34.5%)** show the highest attrition.
- Attrition decreases significantly after the first year.

## By Travel Frequency
- Frequent travelers have the highest attrition rate (**24.9%**), followed by those with some travel (**15%**) and no travel (**8%**).

## By Education
- Employees with **no formal education** have the highest attrition rate (**18.2%**), followed by bachelor's degree holders (**17.3%**).

---

# Recommendations

1. **Improve Onboarding:** Address the high first-year attrition by enhancing the onboarding process.
2. **Revise Travel Policies:** Reduce frequent travel requirements and improve flexibility to lower attrition in this group.
3. **Salary Review:** Address disparities in pay, particularly among employees from "Mixed or multiple ethnic groups."
4. **Focus on High-Risk Roles:** Investigate the challenges faced by sales representatives to mitigate their high turnover.

---

# Conclusion

This analysis highlights key drivers of attrition at Atlas Labs, including seniority, travel, and education level.
By addressing these factors, the company can improve employee retention and foster a more stable and satisfied workforce.
