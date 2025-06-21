# 📘 Web Application Penetration Testing – Database Concepts

## 📁 Data Storage Options

- Text Files  
- Microsoft Excel  
- Microsoft Access  

## 🗃️ Database Management System (DBMS)

A **Database Management System (DBMS)** is software used to manage databases efficiently.

### Common DBMS Platforms:

| DBMS                 | Commonly Used With        |
| -------------------- | ------------------------- |
| MySQL                | PHP                       |
| MariaDB              | PHP                       |
| PostgreSQL           | Python, PHP               |
| Microsoft SQL Server | .NET                      |
| Oracle RDBMS         | Java                      |
| IBM DB2              | Enterprise environments   |
| MongoDB              | NoSQL applications        |
| SQLite               | Mobile & embedded systems |

---

## 📂 What is a Database?

A **database** is an organized collection of data. It stores data in a structured format that is easy to **access**, **read**, and **write**.

### 📊 Advantages over Spreadsheets:

- Handles more data efficiently  
- Organizes data better  
- Provides faster data access  
- Allows complex data manipulation  
- Supports relationships between datasets  

> 📝 *Note: Spreadsheets are optimized for calculations, while databases are optimized for structured data storage and interrelations.*

---

## 🧱 Types of Databases

### 1. **Relational Databases (RDBMS)**

- Use **SQL** (Structured Query Language)  
- Store data in **tables** with defined relationships  

### 2. **NoSQL Databases**

- Not table-based  
- Often **document-oriented** or **key-value** stores  

---

## 🐬 MySQL Overview

- **Open-source and free**  
- **Easy to use** and beginner-friendly  
- **Cross-platform compatibility**  
- Supports multiple languages (PHP, Python, Node.js)  
- **Fast**, reliable, and scalable  

### MySQL Data Types (v8.0)

- **Strong typing system**  
- Numeric types  
- Date and Time types  

---

## 🧩 Database Structure

- **Database** – A set of related tables (1 DB per app recommended)  
- **Table** – Collection of rows and columns for a single entity (e.g., users, products)  
- **Column** – Represents a single field type (e.g., `email`, `first_name`)  
- **Row** – A single data record (e.g., `Rahul`, `Jain`, `rahul@infosec.com`)  
- **Field** – The intersection of a row and column  
- **Index** – Speeds up lookups (like a book index)  
- **Foreign Key** – A reference from one table to another, creating relationships  

---

## 🛠️ CRUD Operations

- **Create**  
- **Read**  
- **Update**  
- **Delete**  

---

## 🖥️ MySQL GUI Tools

- MySQL Workbench  
- DBServer  
- DataGrip  
- HeidiSQL  
- dbForge Studio for MySQL  

---

## 📊 MySQL vs MariaDB vs PostgreSQL

| Feature / Aspect       | MySQL                         | MariaDB                       | PostgreSQL                          |
| ---------------------- | ----------------------------- | ----------------------------- | ----------------------------------- |
| **Ownership**          | Oracle Corporation            | Community-driven (MySQL fork) | PostgreSQL Global Development Group |
| **License**            | GPL v2 + proprietary          | GPL v2                        | PostgreSQL License (MIT-like)       |
| **ACID Compliance**    | Yes (InnoDB engine)           | Yes (InnoDB/MyRocks/Aria)     | Yes (fully ACID compliant)          |
| **SQL Compliance**     | Moderate                      | Better than MySQL             | High (standards-compliant)          |
| **Performance**        | Good for read-heavy loads     | Improved in some workloads    | Great for complex queries/writes    |
| **Storage Engines**    | InnoDB (default), MyISAM      | InnoDB, Aria, MyRocks, TokuDB | Single extensible engine            |
| **JSON Support**       | Partial                       | Same as MySQL                 | Full native JSONB support           |
| **Replication**        | Master-slave, Group Rep       | Galera Cluster built-in       | Logical, physical, streaming        |
| **Partitioning**       | Native                        | Improved                      | Declarative partitioning            |
| **Stored Procedures**  | Yes                           | Yes                           | Yes                                 |
| **Materialized Views** | No                            | No                            | Yes                                 |
| **Full Text Search**   | Limited                       | Improved                      | Advanced (GIN, GiST indexes)        |
| **Extensibility**      | Moderate                      | Moderate                      | High (custom types/functions)       |
| **Community Support**  | Large but Oracle-driven       | Growing, open development     | Strong enterprise/academic support  |
| **Cloud Support**      | Widely supported (AWS, Azure) | Supported (less than MySQL)   | Widely supported (AWS, GCP, Azure)  |

---

## ✅ Strengths Summary

### 🔵 **MySQL**

- Great for web apps (LAMP stack)  
- Stable and well-documented  
- Widely adopted with strong community  

### 🟢 **MariaDB**

- Open-source fork of MySQL with performance improvements  
- More storage engine options  
- Backward compatible with MySQL  

### 🔴 **PostgreSQL**

- Excellent for complex applications  
- Full ACID compliance and advanced querying  
- Ideal for enterprise and data-heavy use cases  
- Extensible and standards-compliant  

---

## 🔐 Resetting MySQL Root Password (Linux)### 🔑 2. Log in Without Password


mysql -u root


### 🧾 Method 1: Using `--skip-grant-tables` (Safe Mode)

> Use this when you can't log in but have system access.

### ✅ Steps:

1. **Stop MySQL Service:**
 
       sudo systemctl stop mysql       # systemd-based systems

       sudo service mysql stop         # SysV-based systems

 3. Log in Without Password

  
        mysql -u root

4. Set New Password:

       For MySQL 5.7 / 8.0+:

5.  FLUSH PRIVILEGES;
 
        ALTER USER 'root'@'localhost' IDENTIFIED BY 'newpassword';

6.  For older MySQL / MariaDB:

        UPDATE mysql.user SET authentication_string=PASSWORD('newpassword') WHERE User='root';
   
        FLUSH PRIVILEGES;

        Stop Safe Mode:

        sudo killall mysqld

        Restart MySQL Normally:

        sudo systemctl start mysql

6. Test Login:

       nmysql -u root -p
