# JDBC PostgreSQL Connection

This project demonstrates how to connect a Java application to a PostgreSQL database using JDBC (Java Database Connectivity).

---

## Prerequisites

- Java JDK 8 or above
- Eclipse/IntelliJ IDEA
- PostgreSQL installed
- PostgreSQL JDBC Driver (`postgresql-<version>.jar`)

---

## Database Configuration

```java
String driver = "org.postgresql.Driver";
String url = "jdbc:postgresql://localhost:5432/mca_25_db";
String username = "postgres";
String password = "your_password";
```

Replace the username and password according to your PostgreSQL installation.

---

## JDBC Connection Steps

### Step 1: Import JDBC Package

```java
import java.sql.*;
```

Imports all required JDBC classes like `Connection`, `DriverManager`, `Statement`, etc.

---

### Step 2: Load JDBC Driver

```java
Class.forName("org.postgresql.Driver");
```

Loads the PostgreSQL JDBC Driver into JVM memory.

**Remember:**  
> No Driver → No Database Connection

---

### Step 3: Create Database URL

```java
String url = "jdbc:postgresql://localhost:5432/mca_25_db";
```

URL Format:

```
jdbc:postgresql://hostname:port/database_name
```

Example:

```
jdbc:postgresql://localhost:5432/mca_25_db
```

Where:

- `jdbc` → Java Database Connectivity
- `postgresql` → Database Type
- `localhost` → Database Server
- `5432` → PostgreSQL Default Port
- `mca_25_db` → Database Name

---

### Step 4: Create Connection

```java
Connection con = DriverManager.getConnection(url, username, password);
```

Creates a connection between Java and PostgreSQL.

---

### Step 5: Check Connection

```java
if(con != null){
    System.out.println("Connected...");
}
```

Verifies whether the database connection was successful.

---

### Step 6: Close Connection

```java
con.close();
```

Always close the connection after completing database operations.

---

## Complete Flow

```
Import Package
       │
       ▼
Load Driver
       │
       ▼
Create URL
       │
       ▼
Username & Password
       │
       ▼
DriverManager.getConnection()
       │
       ▼
Connection Created
       │
       ▼
Perform Database Operations
       │
       ▼
Close Connection
```

---

## Memory Trick

Remember this sequence:

```
Driver
   ↓
URL
   ↓
Username
   ↓
Password
   ↓
Load
   ↓
Connect
   ↓
Check
   ↓
Close
```

Short Formula:

```
D → U → U → P → L → C → C → C
```

Or simply:

```
Load → Connect → Check → Close
```

---

## Common Exceptions

| Exception | Cause |
|-----------|------|
| ClassNotFoundException | JDBC Driver not found |
| SQLException | Wrong URL, username, password, or database not running |
| Connection Refused | PostgreSQL server is stopped |

---

## Expected Output

```
Connected...
```

---


