# 🧠 HR Analytics: Job Change of Data Scientists

## 📌 Introduction
This project analyzes data from candidates who enrolled in the company's **Data Science training program**.  
The goal is to predict whether a candidate is likely to **join the company after completing the course** or is just looking for a job change.

By understanding this behavior, the company can:
- Optimize training costs and resources  
- Improve course planning  
- Better categorize potential candidates

---

## 📊 Data Sources

### 1. Enrollees' Data
Collected from Google Form submissions.

| Column | Description |
|---------|--------------|
| `enrollee_id` | Unique ID of an enrollee |
| `full_name` | Full name of an enrollee |
| `city` | City name |
| `gender` | Gender of the enrollee |

📄 **Source:** [Google Sheet](https://docs.google.com/spreadsheets/d/1VCkHwBjJGRJ21asd9pxW4_0z2PWuKhbLR3gUHm-p4GI/edit?usp=sharing)

---

### 2. Enrollees' Education
Manually collected and stored in Excel format.

| Column | Description |
|---------|--------------|
| `enrollee_id` | Unique ID |
| `enrolled_university` | University enrollment status (`no_enrollment`, `Part time course`, `Full time course`) |
| `education_level` | Highest education attained |
| `major_discipline` | Field of study (e.g., STEM, Business) |

📄 **Source:** [enrollies_education.xlsx](https://assets.swisscoding.edu.vn/company_course/enrollies_education.xlsx)

---

### 3. Working Experience
Collected via manual survey and stored as CSV.

| Column | Description |
|---------|--------------|
| `enrollee_id` | Unique ID |
| `relevent_experience` | Whether experience is relevant |
| `experience` | Total years of work experience |
| `company_size` | Size of previous company |
| `company_type` | Type of previous company |
| `last_new_job` | Years since last job change |

📄 **Source:** [work_experience.csv](https://assets.swisscoding.edu.vn/company_course/work_experience.csv)

---

### 4. Training Hours
Pulled from the **LMS MySQL database**.

**Database Info:**
Host: 112.213.86.31
Port: 3360
Login: etl_practice
Password: 550814
Database: company_course
Table: training_hours

### 5. City Development Index (CDI)
Represents development level of each city.

📄 **Source:** [City Development Index](https://sca-programming-school.github.io/city_development_index/index.html)

---

### 6. Employment
Indicates whether the student started working at the company after the course.

**Database Info:**
Host: 112.213.86.31
Port: 3360
Login: etl_practice
Password: 550814
Database: company_course
Table: employment

## ⚙️ ETL Process
1. **Extract data**

- import data by pandas
2. **Transform**
- Standardized column names and data types
- Cleaned missing values (e.g., replaced `'NA'`, `'None'`, `?`)

3. **Load**
- Exported the cleaned dataset to:
  - `data.csv` for analysis
 
