# Applying Filters to SQL Queries for System Security

This project demonstrates how SQL filters can be used to extract and analyze data for system security management.  
It includes several example queries that filter login attempts and employee data based on conditions such as date, time, location, and department.

---

## 🧠 Skills Demonstrated
- SQL querying
- Data filtering using `WHERE`, `AND`, `OR`, `NOT`, and `LIKE`
- Logical and pattern-based filtering
- Data security investigation with SQL

---

## 🗃️ Tables Used
**log_in_attempts**
| Column | Type | Description |
|--------|------|--------------|
| login_id | INT | Unique ID for each login attempt |
| login_date | DATE | Date of login attempt |
| login_time | TIME | Time of login attempt |
| country | TEXT | Country where login occurred |
| success | BOOLEAN | Whether the login succeeded |

**employees**
| Column | Type | Description |
|--------|------|--------------|
| employee_id | INT | Unique ID for each employee |
| name | TEXT | Employee name |
| department | TEXT | Department of the employee |
| office | TEXT | Building/office location |

---

## 🔍 Example Queries

### 1️⃣ After-Hours Failed Login Attempts
```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00'
  AND success = FALSE;
