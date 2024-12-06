# SQL and ACID

---

## 1. What is SQL?
**SQL (Structured Query Language)** is a standard programming language used to manage and interact with relational databases. It allows users to create, read, update, and delete data stored in database tables.

### Key SQL Operations:
- **DDL (Data Definition Language)**:  
  Defines database structure.  
  - Examples: `CREATE`, `ALTER`, `DROP`.

- **DML (Data Manipulation Language)**:  
  Manipulates data in the database.  
  - Examples: `INSERT`, `UPDATE`, `DELETE`, `SELECT`.

- **DCL (Data Control Language)**:  
  Manages access permissions.  
  - Examples: `GRANT`, `REVOKE`.

- **TCL (Transaction Control Language)**:  
  Manages transactions.  
  - Examples: `COMMIT`, `ROLLBACK`, `SAVEPOINT`.

---

## 2. What is ACID?

**ACID** is a set of properties that ensure reliable and consistent transactions in a database. A transaction is a sequence of operations performed as a single logical unit of work.

### ACID Properties:
1. **Atomicity**:  
   - Ensures that a transaction is "all or nothing."  
   - If any part of the transaction fails, all changes are rolled back, leaving the database unchanged.  
   - Example: Transferring money between bank accounts must either debit and credit both accounts or do nothing at all.

2. **Consistency**:  
   - Ensures that a transaction brings the database from one valid state to another, maintaining all predefined rules (e.g., constraints, triggers).  
   - Example: If a constraint requires a positive account balance, no transaction can result in a negative balance.

3. **Isolation**:  
   - Ensures that concurrent transactions do not interfere with each other.  
   - Each transaction is executed as if it were the only one running.  
   - Example: If two transactions update the same account balance simultaneously, their operations are isolated to prevent race conditions.

4. **Durability**:  
   - Ensures that once a transaction is committed, its changes are permanent, even in case of a system failure.  
   - Example: After a successful money transfer, the updated account balances must persist despite a server crash.

---

## 3. ACID Example
### Scenario: Bank Transfer
- Transaction: Transfer $100 from Account A to Account B.
- SQL Statements:
  ```sql
  BEGIN TRANSACTION;
  UPDATE accounts SET balance = balance - 100 WHERE account_id = 'A';
  UPDATE accounts SET balance = balance + 100 WHERE account_id = 'B';
  COMMIT;
