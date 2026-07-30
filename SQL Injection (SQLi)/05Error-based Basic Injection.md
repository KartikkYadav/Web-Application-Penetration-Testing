
# Error-based Basic Injection
## 🧠 Error-based Basic Injection

### ⚙️ Sql Injection (sqli) Lab setup

**Create a new database named `sqli_db`:**

```sql
CREATE DATABASE sqli_db;

```

**Switch to use the newly created database `sqli_db`:**

```sql
USE sqli_db;

```

**Create a table named `users` with columns for id, name, email, password, and enable status:**

```sql
CREATE TABLE users (
    id INT,                      -- User ID as an integer
    name VARCHAR(50),            -- User’s name, varchar with max length 50
    email VARCHAR(50),           -- User’s email, varchar with max length 50
    password VARCHAR(50),        -- User’s password, varchar with max length 50
    enable INT(1)                -- Status flag indicating if user is enabled (1) or disabled (0)
);

```

**Insert multiple user records into the `users` table:**

```sql
INSERT INTO users(id, name, email, password, enable)
VALUES
(1, 'Krishna', 'Krishna@armour.com', 'e49r034', 1),       -- Enabled user
(2, 'admin', 'admin@armour.com', 'password123', 1),        -- Enabled admin user
(3, 'ankit', 'ankit@armour.com', '123456', 1),             -- Enabled user
(4, 'rahul', 'rahul@armour.com', '123456', 1),             -- Enabled user
(5, 'pooja', 'pooja@armour.com', '123456', 1),             -- Enabled user
(6, 'Vishal', 'Vishal@armour.com', '12343221', 0);         -- Disabled user

```

---

 

## vim connection.php

```php
<?php

// Database connection parameters
$dbhost = "localhost";
$dbuser = "root";
$dbpass = "root";
$dbname = "sqli_db";

// Create connection to MySQL database using mysqli
$connection = mysqli_connect($dbhost, $dbuser, $dbpass, $dbname);

// Check if connection failed and terminate with an error message
if (mysqli_connect_error()) {
    die("Database Connection Failed: " . mysqli_connect_error());
}

?>

```

Description:

This script establishes a connection to the MySQL database `sqli_db` on `localhost` using the username and password `"root"`. It checks for connection errors and stops execution with an error message if the connection fails.

## vim error-based-string.php

<?php

// Include the database connection script
include("connection.php");

?>

<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Error Based String</title>
</head>
<body>

<div style="margin-top:70px; color:#FFF; font-size:23px; text-align:center">
<h1><span class="style4">Error based string:</span><span class="hr">
<font size="3" color="#888888">
<hr>
</font>
</span></h1>
</div>

<?php

// Check if 'id' parameter is passed via GET request
if (isset($_GET['id'])) {

```
// Assign the 'id' parameter value from the GET request to a variable
$sid = $_GET['id'];

// Construct an SQL query to select user record matching the given id
$query = "SELECT * FROM users WHERE id='$sid' LIMIT 0,1";

// Execute the query on the database connection
$result = mysqli_query($connection, $query);

// If the query fails, terminate with error message displaying MySQL error
if (!$result) {
    die('Database Query Failed' . print_r(mysqli_error($connection)));
}

// If successful, fetch the resulting row as an associative array and display user info
while ($row = mysqli_fetch_assoc($result)) {
    echo '<font color="#0000ff">';
    echo 'Your ID: ' . $row['id'];
    echo "<br>";
    echo 'Your User Name: ' . $row['name'];
    echo "</font>";
}

```

}

?>

</body>
</html>

---

The URLs you provided appear to be local addresses accessing the “error-based-string.php” page with different user ID parameters:

- http://192.168.1.31/web-pentest/error-based-string.php?id=1
- http://192.168.1.31/web-pentest/error-based-string.php?id=2
- http://192.168.1.31/web-pentest/error-based-string.php?id=3

Based on the earlier code for “error-based-string.php,” these URLs will run a query to fetch user details for IDs 1, 2, and 3 respectively from the **users** table in the **sqli_db** database.

This page is likely used to demonstrate or test error-based SQL injection vulnerabilities since it accepts the **id** parameter directly into an SQL query without input sanitization or prepared statements.

---

### 🧭 Accessing these URLs will:

- Show user information (ID and username) **if the record is found.**
- If there is a SQL error (e.g., an injection attempt), **it will reveal the database error message because of the error reporting in the PHP code.**

This behavior enables attackers to probe the database structure or test injection payloads by analyzing error messages returned from invalid queries.

If further analysis, exploitation techniques, or mitigation strategies related to this page or SQL injection testing are desired, please specify.

---

### 🧩 id Parameter Behavior

The URLs you provided test the **id** parameter behavior on the error-based injection page with various types of input:

- **id=1** : A normal integer ID that should return the user with ID 1 if existing.
- **id=-1** : A negative number, likely no user with this ID, may lead to no result or error.
- **id=999999999999999999999999999999999999999999999999999999999999999999** :
    
    An extremely large number, probably no matching record, tests how the system handles large values.
    
- **id=admin** : A string instead of an integer, testing type handling and potential error output or injection attempts.

Based on the PHP code, these inputs are directly inserted into the SQL query, so:

- **Numeric values** will be used as-is in the query.
- **String inputs like “admin”** will also be used directly, causing the query to become syntactically incorrect, which may result in a displayed SQL error message.

This is characteristic of an error-based SQL injection vulnerability where database errors help attackers learn about the database structure and behavior.

---

?

---

### 🔥 **Techniques for Error-Based SQL Injection**

### 1️⃣ Using Single Quotes `'` to Test Injection

💉 Inject a single quote `'` to cause syntax error.

⚠️ If error appears, the input is concatenated unsafely.

💡 Try logical payloads like:

```
?id=1' OR '1'='1

```

➡️ to test whether the condition bypasses filters.

---

### 2️⃣ Using SQL Comments to Modify Queries

💬 `%23` or `#` represent comments to ignore the rest of the query.

💬 `--+` is another comment style to safely terminate injected queries.

🧩 **Example:**

```
?id=1' --+
?id=1'%23

```

---

### 3️⃣ Detecting Number of Columns with `ORDER BY`

📊 To craft `UNION` injections, knowing the number of columns returned by the original query helps.

👉 Inject `ORDER BY` with incremental column numbers.

---

---

### 4️⃣ Using `UNION` to Extract Data

💡 **Concept:** `UNION` lets an attacker append results from a crafted query to the application’s original query so they can *read* data returned by the database.

🔎 **What to know:** The injected query must match the original query’s number and type of columns (so results can be combined).

🛡️ **Defensive notes:** Use parameterized queries / prepared statements, restrict database user privileges, validate and limit returned columns, and monitor unusual query patterns.

---

### 5️⃣ Boolean-based (Content-based) Blind SQL Injection

💭 **Concept:** When the application hides error messages, an attacker can infer database information by sending queries that evaluate to TRUE or FALSE and observing changes in page content/behavior.

🔬 **What to know:** The attacker learns data bit-by-bit by turning questions into true/false tests. This is slow and noisy.

🛡️ **Defensive notes:** Use prepared statements, enforce input validation, normalize outputs to avoid revealing differences, add rate limits, and use WAFs/IDS to detect repetitive probing.

---

### 6️⃣ Time-based & Out-of-Band (OOB) Techniques

⏳ **Time-based Concept:** The attacker causes the database to delay its response conditionally; the response time reveals whether a condition is true.

🌐 **OOB Concept:** The attacker forces the database to make an external connection or trigger an out-of-band channel (useful when direct responses are suppressed).

🛡️ **Defensive notes:** Limit database ability to make external network connections, monitor and block suspicious outbound traffic, enforce query timeouts, and log anomalous long-running queries.

---

---

### 🔁 `UNION` vs `UNION ALL` — quick summary

- `UNION`
    - Combines result sets from multiple `SELECT`s and **removes duplicate rows**.
    - Has an implicit deduplication step (which can cost extra CPU/time).
- `UNION ALL`
    - Combines result sets **without removing duplicates** — faster because no dedupe step.

---

### 🔗 Chaining multiple `UNION` / `UNION ALL`

- You can chain many `SELECT` blocks:
    
    ```
    SELECT col1, col2 FROM tableA
    UNION ALL
    SELECT col1, col2 FROM tableB
    UNION ALL
    SELECT col1, col2 FROM tableC;
    
    ```
    
- **Rules:** every `SELECT` in the chain must return the **same number of columns**, and corresponding columns should be **type-compatible** (or cast explicitly).
- Parentheses can group parts when using `ORDER BY`, `LIMIT`, or when mixing `UNION` with other constructs.

---

### ⚙️ Performance & behavior notes

- `UNION` does a dedupe step (sort/unique) — may be slower and memory-using for large sets.
- `UNION ALL` is generally faster and preserves duplicates.
- Use appropriate indexes on underlying tables; consider `LIMIT`/paging if result sets are large.

---

### ✅ Harmless example (legitimate use case)

```
-- Combine active customers and trial users into one feed
SELECT id, name, email FROM customers WHERE status = 'active'
UNION ALL
SELECT id, name, email FROM trials WHERE expires_at > CURRENT_DATE;

```

---

### 🛡️ Security & defensive best practices

- **Don't** rely on client-side filtering — validate on server side.
- **Use parameterized queries / prepared statements** everywhere (prevents injection).
- **Least privilege:** DB user should only have SELECT on allowed tables/columns.
- **Monitor & alert:** queries with multiple `UNION` (or suspiciously many columns) can indicate probing — log and alert on them.
- **Limit result sizes** and enforce reasonable query timeouts.
- **WAF/IDS:** create rules to detect common injection patterns and high-frequency probing.
- **Sanitize/whitelist** any user-supplied identifiers (if you must allow dynamic table/column names).

---
