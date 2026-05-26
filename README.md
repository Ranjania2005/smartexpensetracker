
##  Smart Expense Tracker

A simple Java console application for tracking student expenses using MySQL and JDBC.

## Project Features

- Menu-driven console application
- Java OOP design with packages: `model`, `service`, `db`, `util`, `main`
- JDBC connectivity with MySQL
- Collections-based expense handling
- Exception handling for database and input operations
- Expense persistence in MySQL
- Monthly summaries, budget warnings, category totals, sorting and search

## Expense Fields

- `expense id`
- `title`
- `amount`
- `category`
- `date`

## Project Structure

- `src/main/java/com/example/smartexpensetracker/db/DbConnection.java`
- `src/main/java/com/example/smartexpensetracker/model/Expense.java`
- `src/main/java/com/example/smartexpensetracker/service/ExpenseService.java`
- `src/main/java/com/example/smartexpensetracker/util/InputUtil.java`
- `src/main/java/com/example/smartexpensetracker/main/ExpenseTrackerApp.java`
- `src/main/java/com/example/smartexpensetracker/SmartexpensetrackerApplication.java`

## Database Setup

1. Start MySQL server.
2. Create the database and table using the SQL script in `schema.sql`.
3. Update `DbConnection` with your MySQL username and password.

### Sample SQL schema

```sql
CREATE DATABASE IF NOT EXISTS expense_tracker;
USE expense_tracker;

CREATE TABLE IF NOT EXISTS expenses (
  id INT AUTO_INCREMENT PRIMARY KEY,
  title VARCHAR(100) NOT NULL,
  amount DOUBLE NOT NULL,
  category VARCHAR(50) NOT NULL,
  date DATE NOT NULL
);
```

## Configuration

In `src/main/java/com/example/smartexpensetracker/db/DbConnection.java`, update:

```java
private static final String DB_USER = "root";
private static final String DB_PASSWORD = "password";
```

If your MySQL server runs on another port or host, update the `DB_URL` accordingly.

## Build and Run

From the project root:

```bash
mvn clean compile exec:java
```

Or build a jar and run:

```bash
mvn clean package
java -cp target/smartexpensetracker-0.0.1-SNAPSHOT.jar com.example.smartexpensetracker.SmartexpensetrackerApplication
```

## Sample Console Output

```
Smart Expense Tracker
--------------------
This simple console app saves expenses to MySQL.

Menu:
1. Add expense
2. View all expenses
3. Search expenses by category
4. Monthly expense summary
5. Budget limit warning
6. Delete expense
7. Sort expenses by amount
8. Category-wise total
9. Retrieve saved data from database
10. Exit system
Choose an option: 1
Enter title: Stationery
Enter amount: 12.50
Enter category: Study
Enter date (YYYY-MM-DD): 2026-05-25
Expense added successfully.

Menu:
1. Add expense
...
```

## Notes

- The app is intentionally simple and student-friendly.
- It demonstrates JDBC, collections, exception handling, and basic SQL operations.
- The menu design is kept clear for a console-based internship project.
#
