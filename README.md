

🌍 World Layoffs Project 📉

The **World Layoffs** project provides insights into the global trend of layoffs across industries. The project uses MySQL to store and manage data related to employee layoffs in various companies. By analyzing this data, i aim to track and visualize the impact of job losses around the world.

This repository includes a comprehensive database structure for storing layoff-related data, as well as scripts for data insertion and querying.

---

🧑‍💻 **Features**
- A MySQL database schema to store detailed information about layoffs.
- Provides records of various companies, number of layoffs, job positions affected, and other relevant information.
- Queries for generating detailed reports and visualizing the trend of global layoffs over time.

---

🔧 **Technologies Used**
- **MySQL**: For data storage and management.
- **SQL Queries**: To retrieve and analyze layoff data.
- **Python** (Optional): For further data analysis and reporting (if applicable).
- **PHP/JavaScript** (Optional): For front-end interfaces or data visualization (if applicable).

---

📊 **Data Structure**

The database consists of several tables that store information related to layoffs. Here’s an example of the key tables:

1. **Companies**: Stores details about each company.
    - `company_id` (INT, Primary Key)
    - `company_name` (VARCHAR)
    - `industry` (VARCHAR)
    - `country` (VARCHAR)

2. **Layoffs**: Stores information about individual layoffs.
    - `layoff_id` (INT, Primary Key)
    - `company_id` (INT, Foreign Key)
    - `layoff_date` (DATE)
    - `num_employees_affected` (INT)
    - `job_positions_affected` (VARCHAR)

3. **Employees**: Optional table for detailed employee-level information.
    - `employee_id` (INT, Primary Key)
    - `company_id` (INT, Foreign Key)
    - `employee_name` (VARCHAR)
    - `layoff_status` (ENUM: 'laid_off', 'not_laid_off')

---

🚀 **Getting Started**

To get started with the **World Layoffs** project, follow these steps:

### 1. Clone the repository:


git clone https://github.com/Sidharth76/World-Layoffs.git


2. Set up MySQL database:

- Create a MySQL database and import the schema provided in the `schema.sql` file.
- You can use any MySQL client (e.g., MySQL Workbench, phpMyAdmin) to import the schema.
  
```sql
CREATE DATABASE world_layoffs;
USE world_layoffs;
SOURCE path_to_your_schema.sql;
```

3. Insert Data:

You can either manually insert data into the database or use the `insert_data.sql` script provided in the repository to populate the database with some sample data.

4. Run Queries:

Use the MySQL command line or any MySQL client to run SQL queries on the database. Example query to find total layoffs by country:

```sql
SELECT country, SUM(num_employees_affected) as total_layoffs
FROM layoffs
JOIN companies ON layoffs.company_id = companies.company_id
GROUP BY country;
```

5. Optional: Frontend/Backend Integration:

You can integrate the data with a backend (like Python or Node.js) to create a more interactive platform or visualization tool for users to explore the layoff data.

---

📚 **Database Schema**

Below is a sample schema for the database:

```sql
-- Create Companies table
CREATE TABLE companies (
  company_id INT AUTO_INCREMENT PRIMARY KEY,
  company_name VARCHAR(255),
  industry VARCHAR(255),
  country VARCHAR(100)
);

-- Create Layoffs table
CREATE TABLE layoffs (
  layoff_id INT AUTO_INCREMENT PRIMARY KEY,
  company_id INT,
  layoff_date DATE,
  num_employees_affected INT,
  job_positions_affected VARCHAR(255),
  FOREIGN KEY (company_id) REFERENCES companies(company_id)
);
```



🗣️ **Contact**

If you have any questions or suggestions, feel free to open an issue or contact the repository owner directly.

- GitHub: [@Sidharth76](https://github.com/sidharth76)
```
