# 💳 Banking Management System

A simple **Banking Management System** built in Java using JDBC and MySQL that allows users to register, log in, open bank accounts, and perform common banking operations like deposit, withdrawal, balance check, and money transfer.

## 🚀 Features

* **User Registration & Login**
  * New users can register with full name, email, and password.
  * Existing users can log in securely.

* **Account Management**
  * Open a new bank account linked to the user’s email.
  * Automatically generate a unique account number.
  * Secure account access with a 4-digit security PIN.

* **Banking Operations**
  * **Credit Money:** Add funds to your account.
  * **Debit Money:** Withdraw funds securely.
  * **Transfer Money:** Send money to another account.
  * **Check Balance:** View current account balance.

* **Transaction Management**
  * Uses SQL transactions (`commit` and `rollback`) to ensure data consistency.
  * Prevents overdrafts and invalid transfers.


## 🛠️ Technologies Used

* **Language:** Java
* **Database:** MySQL
* **JDBC:** Java Database Connectivity
* **IDE (optional):** IntelliJ IDEA / Eclipse / VS Code

---


**Create the tables**

   ```sql
   CREATE TABLE user(
       full_name VARCHAR(255) NOT NULL,
       email VARCHAR(255) NOT NULL PRIMARY KEY,
       password VARCHAR(255) NOT NULL
   );

   CREATE TABLE accounts(
       account_number BIGINT NOT NULL PRIMARY KEY,
       full_name VARCHAR(255) NOT NULL,
       email VARCHAR(255) NOT NULL UNIQUE,
       balance DECIMAL(10,2) NOT NULL,
       security_pin CHAR(4) NOT NULL
   );
   ```

 **Update the database connection details** in `BankingApp.java`:

   ```java
   private static final String url = "jdbc:mysql://localhost:3306/banking_system";
   private static final String username = "root";
   private static final String password = "Admin@123";
   ```



## 🧩 How It Works

1. Run the application.
2. Choose **Register** to create a new user account.
3. Log in using your email and password.
4. Open a new bank account with an initial deposit and PIN.
5. Perform any operation:

   * Debit / Credit / Transfer money
   * Check balance
6. Log out or exit the system safely.

---

## 🔒 Security Features

* Password and PIN validation before sensitive operations.
* SQL prepared statements to prevent SQL injection.
* Transaction rollback for failed operations to maintain data integrity.


