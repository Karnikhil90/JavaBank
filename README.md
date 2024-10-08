# JavaBank: Simple Banking Simulation

JavaBank is a simple command-line banking application that allows users to create accounts, log in securely, and manage their finances through basic operations like deposits, withdrawals, and money transfers. The application provides persistent data storage, allowing users to resume their banking activities even after closing the application.

## Application Flow

1. **Start**:
   - When the application starts, the user is presented with two options:
     1. Log in
     2. Create a new account

2. **Creating a New Account**:
   - If the user selects "Create a new account," they will be prompted to provide:
     - Account holder's name
     - A username (for login)
     - A password (for secure login)
     - An initial deposit (optional)
   - A unique account number is generated automatically, and the account is created with an initial balance. The user will then be asked if they want to log in or exit the application.

3. **Logging In**:
   - If the user selects "Log in," they will be asked to enter their username and password. If the credentials match an existing account, they will be granted access to their account and presented with the following options:
     1. Deposit Money
     2. Withdraw Money
     3. Transfer Money Between Accounts
     4. Check Account Balance
     5. View Transaction History
     6. Logout
     7. Exit

4. **After Login**:
   - Once logged in, users can choose any of the available banking operations:
     - **Deposit Money**: Enter the amount to deposit and update the balance.
     - **Withdraw Money**: Enter the amount to withdraw, and if sufficient funds are available, the balance is reduced.
     - **Transfer Money**: Enter the recipient’s account number and the amount to transfer. The system checks the sender’s balance and logs the transfer.
     - **Check Balance**: View the current balance of the logged-in account.
     - **View Transaction History**: See a detailed list of deposits, withdrawals, and transfers.
     - **Logout**: Log out and return to the login screen.
     - **Exit**: Close the application.

5. **Logging Out**:
   - Users can log out at any time. This will clear the current session and return them to the login screen.

6. **Exit**:
   - Users can exit the application, and all account data, including transaction history and balances, will be saved for future sessions.

## For Developers

### Data Storage and Persistence

- The application stores user data in text files to ensure persistence across sessions. Two key files and directories are used:
  
  1. **Login Credentials File**:
     - This file stores each user's **username**, **password**, and a unique **hash ID**.
     - The hash ID links to the user's account for faster access during login.
     - Each user is required to log in using their username and password before accessing their account.

  2. **User Data Directory**:
     - A dedicated directory is created for each user upon account creation.
     - The directory is named using the unique hash ID and contains two main files:
       - `current_balance.txt`: Stores the user’s current account balance.
       - `transaction_history.txt`: Logs all transactions (deposits, withdrawals, and transfers) associated with the account.
     - Each time a user performs a transaction, the data in these files is updated to ensure all account activities are tracked and persisted.

### Example Directory Structure

```
/data/
  credentials.txt (stores user login info with username, password, hash ID)
  /users/
    /user_hash_id_1/ 
      current_balance.txt (stores balance for user 1)
      transaction_history.txt (logs all transactions for user 1)
    /user_hash_id_2/
      current_balance.txt (stores balance for user 2)
      transaction_history.txt (logs all transactions for user 2)
```

### File Read/Write Operations

- **Login Credentials File**:
  - The file containing usernames, passwords, and hash IDs is read during login to authenticate users.
  - This file is written to when a new account is created.
  
- **User Data Directory**:
  - Each user’s account data is read from their respective directory during login.
  - For every transaction, the `current_balance.txt` and `transaction_history.txt` files are updated in real-time.

### Future Improvements
- The application could be extended to support additional features such as:
  - Interest calculation for account balances.
  - More robust password security using hashing algorithms.
  - A graphical user interface (GUI) for enhanced user interaction.



## Features

- **Create a New Account**:
  - Users can create new accounts by providing basic details like their name, username, password, and an initial deposit.
  - A unique account number is automatically generated for each user.

- **Login**:
  - Users can securely log into their accounts using their username and password.
  - Once logged in, users can access various banking operations.

- **Deposit Money**:
  - Logged-in users can deposit money into their accounts. The amount is added to the current balance, and the transaction is logged.

- **Withdraw Money**:
  - Users can withdraw money from their accounts, provided they have sufficient funds. The system checks the balance before allowing the withdrawal, and the transaction is logged.

- **Transfer Money Between Accounts**:
  - Users can transfer money to other accounts by entering the recipient's account number and the amount to transfer. The system ensures that the sender has sufficient funds and logs the transaction.

- **Check Account Balance**:
  - Users can check the current balance of their account at any time during their session.

- **View Transaction History**:
  - The application provides a detailed transaction history for each account, showing all deposits, withdrawals, and transfers.

- **Logout**:
  - Users can log out of their session, returning them to the login screen. This allows multiple users to interact with the system without exiting the application.

- **Exit**:
  - The user can exit the application at any time, and all account data is saved for future sessions.

---

With this structure, the **JavaBank** simulation ensures persistent, secure, and scalable account management, suitable for learning purposes or as a base for more complex systems.

---
## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.



## About Me

Self-taught coder | Still Learning | Fluent in Java❤️ & Python | C/C++, Rust, & Basic Web Development | Passionate about Embedded Systems ❤️

### Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/karnikhil90/)
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://x.com/karnikhil90)
[![Social Media](https://img.shields.io/badge/Social%20Media-000000?style=for-the-badge&logo=google&logoColor=white)](https://linktr.ee/karnikhil90)
