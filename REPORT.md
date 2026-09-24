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

### 2.2.3 Constraints

The Bank Account Simulator will operate under the following design constraints:

1. **Reliability:** The system shall prevent a withdrawal or transfer from
   being completed when the requested amount exceeds the available balance.

2. **Data Integrity:** A rejected transaction shall not modify the balance
   of any affected account.

3. **Security and Access:** Only an authenticated user shall be permitted
   to perform transactions on an account associated with that user.

4. **Economic:** The application shall be developed using freely available
   development and testing tools and shall not require paid third-party
   services to operate.

5. **Sustainability:** The application shall operate entirely as a software
   simulation and shall not require dedicated physical banking hardware.

6. **Ethics:** The application shall use simulated account and transaction
   data and shall not require users to provide real banking credentials or
   real financial account information.

7. **MVC Architecture:** The application shall follow the Model-View-Controller
   (MVC) architecture as required by the project specification.

8. **Testing:** Automated unit tests shall be implemented using JUnit where
   applicable.
