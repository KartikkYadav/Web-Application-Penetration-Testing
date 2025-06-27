# 🔵 Data Manipulation Language (DML) 

---

## 1️⃣ SELECT – Retrieve Data

### ✅ Example 1: Get all employee details
    
    SELECT * FROM Employees;

### ✅ Example 2: Get names and salaries of employees in IT department

    SELECT EmpName, Salary
    FROM Employees
    WHERE Department = 'IT';

### ✅ Example 3: Get employees with salary between 40000 and 60000

    SELECT EmpName, Salary
    FROM Employees
    WHERE Salary BETWEEN 40000 AND 60000;

### ✅ Example 4: Sort employees by salary (descending)

    SELECT EmpName, Salary
    FROM Employees
    ORDER BY Salary DESC;
### ✅ Example 5: Find distinct departments

    SELECT DISTINCT Department
    FROM Employees;

## 2️⃣ INSERT – Add Data

### ✅ Example 1: Insert a full record

    INSERT INTO Employees (EmpID, EmpName, Department, Salary)
    VALUES (301, 'David', 'Marketing', 52000);

### ✅ Example 2: Insert only into selected columns

    INSERT INTO Employees (EmpName, Department)
    VALUES ('Eva', 'Finance');

### ✅ Example 3: Insert multiple rows at once

    INSERT INTO Employees (EmpID, EmpName, Department, Salary)
    VALUES 
    (302, 'Sara', 'IT', 60000),
    (303, 'Liam', 'Sales', 45000);

## 3️⃣ UPDATE – Modify Data

### ✅ Example 1: Update salary for one employee

    UPDATE Employees
    SET Salary = 58000
    WHERE EmpID = 301;

## ✅ Example 2: Increase salary by 10% for IT department

    UPDATE Employees
    SET Salary = Salary * 1.10
    WHERE Department = 'IT';

## ✅ Example 3: Set department to "Admin" for employees with null department

    UPDATE Employees
    SET Department = 'Admin'
    WHERE Department IS NULL;

## 4️⃣ DELETE – Remove Data

### ✅ Example 1: Delete one specific employee

    DELETE FROM Employees
    WHERE EmpID = 303;

### ✅ Example 2: Delete employees with salary less than 30000

    DELETE FROM Employees
    WHERE Salary < 30000;

### ✅ Example 3: Delete all employees in the "Temporary" department

    DELETE FROM Employees
    WHERE Department = 'Temporary';

## ✅ Example 4: Delete all rows (⚠️ Dangerous)

    DELETE FROM Employees;

## ⚙️ Advanced Examples

### 🔄 Insert using SELECT from another table

    INSERT INTO BackupEmployees (EmpID, EmpName, Salary)
    SELECT EmpID, EmpName, Salary
    FROM Employees
    WHERE Department = 'HR';

### 🧾 Conditional SELECT with IN

    SELECT EmpName, Department
    FROM Employees
    WHERE Department IN ('IT', 'HR');

### 🔍 Pattern matching with LIKE

    SELECT EmpName
    FROM Employees
    WHERE EmpName LIKE 'A%'; -- Names starting with A

### 📌 Practice Table (for reference)

You can use this sample table to practice:

    CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    EmpName VARCHAR(100),
    Department VARCHAR(50),
     Salary DECIMAL(10,2)
    );
