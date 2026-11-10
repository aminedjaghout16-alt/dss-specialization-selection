# DSS - University Specialization Selection

Web app (PHP + MySQL) using the Weighted Sum Model (WSM).

## Run it (Windows, XAMPP)
1. Install XAMPP and start **Apache** and **MySQL** in the XAMPP Control Panel.
2. Copy this whole folder to `C:\xampp\htdocs\dss`.
3. Open http://localhost/phpmyadmin -> tab **Import** -> choose `database.sql` -> **Go**.
4. Open http://localhost/dss/

If your MySQL has a password, edit `config.php`.

## Files
| File | Role |
|---|---|
| database.sql | Tables + sample data |
| config.php | DB connection |
| students.php / specializations.php / criteria.php | CRUD pages |
| evaluations.php | Enter scores (1-10) per student |
| results.php | WSM calculation, ranking, chart, recommendation, tie detection |
| header.php / footer.php / style.css | Layout |

## WSM method
- Normalization: maximize `r = x / 10`, minimize `r = (11 - x) / 10`
- Score(Pi) = sum of (weight_j x r_ij)
- Ranking = descending score; highest = recommendation; equal scores (4 decimals) = tie.
