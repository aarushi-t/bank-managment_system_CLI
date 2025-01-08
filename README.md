# bank-managment_system_CLI
this is the bank management project (backend) the CLI version 
# virtual environment
create a virtual environment as the first step
**Libraries**
pip install pymysql, colorama, pyttsx3
 Create a MySQL database named `db_bank` and add the necessary tables using the provided SQL script (`db_bank.sql`).
 
**Usage**
-----
1.  Run the `main.py` script to start the banking system.
2.  Follow the on-screen instructions to register, login, and perform various banking operations.

**Code Structure**
-----------------
The code is organized into the following modules:

*   `models.py`: Defines the database models and functions for interacting with the database.
*   `services.py: Provides functions for performing various banking operations, such as account creation, deposit, and withdrawal.
*   `views.py`: Handles user input and output, including registration, login, and account management.
*   `controllers.py`: Coordinates the flow of the application, including user authentication and authorization.
*   `decorator.py`: Defines a decorator for logging transactions.

**Database Schema**
------------------
The database schema is defined in the `db_bank.sql` script and consists of the following tables:

*   `bank_login`: Stores user login credentials.
*   `bank_details`: Stores user account information.
*   `transactions`: Stores transaction history.
**Security**
------------
The application uses password validation and hashing to ensure secure storage of user passwords. 
Additionally, the `pyttsx3` library is used to provide text-to-speech functionality for visually impaired users.

**Detailed Explanation**
----------------------
### Models

The `models.py` module defines the database models and functions for interacting with the database. It includes the following classes and functions:

*   `BankAccount`: Represents a bank account and provides methods for deposit, withdrawal, balance inquiry, and transaction history.
*   `BankService`: Provides functions for performing various banking operations, such as account creation, deposit, and withdrawal.
*   `get_accounts()`: Retrieves a list of all account numbers from the `bank_login` table.
*   `get_password(acc_no)`: Retrieves the password for a given account number from the `bank_login` table.
*   `open_account(acc_no, name, age, contact, address, balance)`: Creates a new account in the `bank_details` table.
*   `get_account_details(acc_no)`: Retrieves the account details for a given account number from the `bank_details` table.
*   `add_balance(acc_no, amount)`: Adds a specified amount to the balance of a given account number.
*   `debit_balance(acc_no, amount)`: Deducts a specified amount from the balance of a given account number.
*   `delete_account(acc_no)`: Deletes an account from the `bank_details` table.
*   `withdraw(amount, acc_no)`: Withdraws a specified amount from a given account number.
*   `create_login(acc_no, password)`: Creates a new login entry in the `bank_login` table.
*   `get_balance(acc_no)`: Retrieves the balance for a given account number from the `bank_details` table.
*   `show_transaction(acc_no)`: Retrieves the transaction history for a given account number from the `transactions` table.
*   `add_trans(acc_no, trans_type, amount, to_user)`: Adds a new transaction to the `transactions` table.
*   `show_log(acc_no)`: Retrieves the log details for a given account number from the `transactions` table.

### Services

The `services.py` module provides functions for performing various banking operations, such as account creation, deposit, and withdrawal. It includes the following classes and functions:

*   `BankService`: Provides functions for performing various banking operations, such as account creation, deposit, and withdrawal.
*   `connect_to_database()`: Establishes a connection to the MySQL database.
*   `under_age(age)`: Checks if the age is within the valid range (18-130).
*   `wrong_contact(contact)`: Checks if the contact number is valid (10 digits and numeric).
*   `account_check(acc_no)`: Checks if an account exists in the `bank_login` table.
*   `balance_check(acc_no, amount)`: Checks if the balance is sufficient for a withdrawal.
*   `password_check(password)`: Checks if the password meets the security requirements (at least one number and one symbol).

### Views

The `views.py` module handles user input and output, including registration, login, and account management. It includes the following classes and functions:

*   `BankAccount`: Represents a bank account and provides methods for deposit, withdrawal, balance inquiry, and transaction history.
*   `open_acc()`: Creates a new account.
*   `login()`: Logs in to an existing account.
*   `deposit()`: Deposits money into an account.
*   `withdraw()`: Withdraws money from an account.
*   `acc_details()`: Displays account details.
*   `log_details()`: Displays log details.
*   `close_acc()`: Closes an account.
*   `transaction_neft()`: Transfers money between accounts.
*   `trans_history()`: Displays transaction history.

### Controllers

The `controllers.py` module coordinates the flow of the application, including user authentication and authorization. It includes the following classes and functions:

*   `operations()`: Coordinates the flow of the application.

### Decorator

The `decorator.py` module defines a decorator for logging transactions. It includes the following functions:

*   `log_transaction()`: Logs transactions.
