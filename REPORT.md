# Ense-375 Software Testing and Validation 

## Bank Account Simulator

### Team Members
- Robert Calinescu
- Ethan Behl
- Jeremiah Onunkwo

## 2.    Design Problem
### 2.1 Problem Definition:  Bank Account Simulator
           
Bank account users need a safe and reliable way to perform basic financial transactions like depositing funds, withdrawing funds, transferring money between accounts, and checking account balances. These operations must be processed accurately because invalid transactions, incorrect balance calculations, or improper handling of insufficient funds can result in inaccurate account information.

The proposed solution  is to develop a simple Bank Account Simulator that provides a controlled environment for performing and testing basic banking operations. The application will process valid transactions while appropriately rejecting invalid transactions that could place an account in an invalid state. The system will provide consistent and predictable behaviour for deposits, withdrawals, transfers, and balance inquiries while maintaining accurate account balances

### 2.2 Design Requirements

#### 2.2.1 Functions
The Bank Account Simulator will provide the following functions:

- Create a bank account with an initial balance.
- Deposit funds into an account.
- Withdraw funds from an account.
- Transfer funds from one account to another.
- Display the current balance of an account.
- Validate transaction inputs before processing them.
- Reject invalid transactions, such as transactions with invalid amounts or insufficient funds.
- Update account balances after successful transactions.
- Record completed transactions for later viewing.
- Display appropriate confirmation or error messages based on the result of a transaction.
