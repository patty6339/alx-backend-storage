# alx-backend-storage

Here are concise notes on the topics you requested:

### 1. **Creating Tables with Constraints in MySQL**
   - **Constraints** are rules enforced on data in a table to ensure data integrity.
   - Common types of constraints include:
     - **PRIMARY KEY**: Ensures unique values in a column or set of columns.
     - **FOREIGN KEY**: Links one table to another, ensuring referential integrity.
     - **UNIQUE**: Ensures all values in a column are distinct.
     - **NOT NULL**: Ensures a column cannot have a NULL value.
     - **CHECK**: Ensures that values in a column meet a specified condition.

   **Example:**
   ```sql
   CREATE TABLE Employees (
       ID INT NOT NULL PRIMARY KEY,
       Name VARCHAR(100),
       Age INT CHECK (Age >= 18),
       DepartmentID INT,
       FOREIGN KEY (DepartmentID) REFERENCES Departments(ID)
   );
   ```

### 2. **Optimizing Queries by Adding Indexes**
   - **Indexes** improve query performance by allowing the database to find rows faster.
   - Types of indexes:
     - **Single-column index**: On one column.
     - **Multi-column (composite) index**: On multiple columns.
     - **Unique index**: Ensures that values are unique in the indexed column.
   
   **When to use indexes**:
   - On columns used frequently in WHERE clauses.
   - On columns used in JOINs, ORDER BY, or GROUP BY.
   
   **Example:**
   ```sql
   CREATE INDEX idx_employee_name ON Employees(Name);
   ```

### 3. **Stored Procedures and Functions in MySQL**
   - **Stored Procedures**: Predefined SQL code that performs operations and can take input/output parameters. They do not return values.
   - **Functions**: Similar to stored procedures but they return a single value and are often used in SQL statements.
   
   **Stored Procedure Example:**
   ```sql
   DELIMITER //
   CREATE PROCEDURE GetEmployeeDetails(IN empID INT)
   BEGIN
       SELECT * FROM Employees WHERE ID = empID;
   END //
   DELIMITER ;
   ```

   **Function Example:**
   ```sql
   DELIMITER //
   CREATE FUNCTION CalculateBonus(salary DECIMAL) RETURNS DECIMAL
   BEGIN
       RETURN salary * 0.10;
   END //
   DELIMITER ;
   ```

### 4. **Views in MySQL**
   - **Views** are virtual tables based on the result of a SELECT query. They provide an abstracted way of looking at data without storing it physically.
   - Views simplify complex queries and enhance security by limiting access to specific data.
   
   **How to Create a View:**
   ```sql
   CREATE VIEW EmployeeView AS
   SELECT Name, DepartmentID FROM Employees WHERE Age > 25;
   ```
   
   **Using the View:**
   ```sql
   SELECT * FROM EmployeeView;
   ```

### 5. **Triggers in MySQL**
   - **Triggers** are database operations that are automatically executed (or "triggered") when certain events (like INSERT, UPDATE, DELETE) occur on a table.
   - Triggers can enforce business rules, update audit trails, or prevent invalid data modifications.

   **How to Create a Trigger:**
   ```sql
   DELIMITER //
   CREATE TRIGGER BeforeInsertEmployee
   BEFORE INSERT ON Employees
   FOR EACH ROW
   BEGIN
       IF NEW.Age < 18 THEN
           SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'Age cannot be less than 18';
       END IF;
   END //
   DELIMITER ;
   ```

These concepts are fundamental in database design, query optimization, and maintaining data integrity in MySQL.