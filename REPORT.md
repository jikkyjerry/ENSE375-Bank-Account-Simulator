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

#### 2.2.2 Objectives
The objective of the Bank Account Simulator is to have the majority of the features expected in a regular banking app, scaled down to an appropriate scope for the class and testing goals. The objectives are:
- To provide users with a personal bank account simulation. 
- To provide users with transactional capabilities with their simulated bank account, including but not limited to deposits, withdrawals, and transfers.
- To validate the above transactions before confirmation.
- To provide sub-accounts that the user can create within their overall simulated account.
- To provide a transaction history for users to review and confirm transactions.
- To provide account sign-in and value validation through the implementation of MVC architecture.
- To provide transaction capabilities between multiple user-created accounts.
- To orient the simulator in a way to demonstrate various testing methods as needed.

### 2.2.3 Constraints

The Bank Account Simulator will operate under the following design constraints:

1. **Reliability:** The system shall prevent a withdrawal or transfer from
   being completed when the requested amount exceeds the available balance.

2. **Data Integrity:** A rejected transaction shall not modify the balance
   of any affected account.

3. **Security and Access:** The application shall require users to log in using valid credentials before accessing their simulated bank accounts or performing transactions. Authentication shall be handled within the application without relying on external authentication services.

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

## 3. Solution 
Two possible designs were considered for the Bank Account Simulator so far. Both designs use the required Model View Controller architecture but they differ in how application responsibilities are separated. The designs were evaluated according to testability, separation of concerns, reliability and maintainability, and ability to support the required testing techniques. These techniques include path testing, data-flow testing, integration testing, boundary-value analysis, equivalence-class testing, decision-table testing, state-transition testing, and use-case testing. 
### 3.1 Solution 1: Basic MVC Design
#### 3.1.1 Design Description
The first solution uses a basic MVC architecture. 
The View provides a simple interface through which the user can:
- log in
- create or select accounts
- view account balances
- deposit/withdraw/transfer funds
- view transaction history.

The Controller receives user requests from the View and contains the majority of the application’s processing and validation logic. The responsibilities include:
- validates transaction values
- verifies available balances
- processes deposits, withdrawals, and transfers
- performs login validation
- determines whether an operation should be accepted or rejected.
- Coordinating account updates and transaction history

The Model stores application data including: users, accounts, balances, sub-accounts, and transaction history. Successful operations performed through the Controller update the corresponding Model data. 

#### 3.1.2 Testing Advantages
Solution 1 provides useful opportunities for testing. Because the application follows MVC, Model and Controller logic can be tested separately of the user interface. Deposit, withdrawal, and transfer amounts provide good inputs for boundary-value analysis and equivalence-class testing. Transaction processing also contains conditional branches that make it possible to perform path testing and decision table testing. 

#### 3.1.3 Weaknesses: 
The main weakness of Solution 1 is that too much responsibility is concentrated in the Controller. The Controller is responsible for authentication, transaction validation, transaction processing, balance checking, account management, and transaction history management. This makes unit testing less isolated because everything is mixed together. Validation rules are also harder to test independently because they are not separated into their own component. Integration testing becomes less clearly divided because many application responsibilities depend on the same Controller. Another limitation is that although transaction history is stored, transactions are not represented as strongly separated objects or states. It becomes more difficult to examine and test the lifecycle of a transaction. State transition testing is also limited as this design doesn’t have enough account states to test. 


### 3.2 Solution 2: Improved MVC Design

#### 3.2.1 Design Description

Solution 2 improves the first design by separating transaction processing, validation, authentication, and account management into smaller, more focused functions and classes. This makes the Bank Account Simulator easier to maintain, test, and debug.

Instead of having one Controller handle most of the application logic, the Controller coordinates requests between the View and specialized Model components. These components handle user registration and login, account and sub-account management, deposits, withdrawals, transfers, and transaction history.

Additionally, the design introduces clearer account states, such as Active and Deactivated, to support state-transition testing. This modular approach improves the separation of responsibilities while maintaining the MVC architecture.

#### 3.2.2 Testing Advantages

Solution 2 offers the following testing advantages:

1. **Unit Testing:** Smaller, independent functions make it easier to test individual operations such as deposits, withdrawals, transfers, and authentication.

2. **Boundary-Value and Equivalence-Class Testing:** Transaction amounts, account balances, and password requirements provide clear valid and invalid test cases.

3. **Decision-Table Testing:** Different combinations of conditions, such as available balance, transaction amount, and account status, can be tested systematically.

4. **State-Transition Testing:** Clearly defined account states allow testing of valid and invalid operations under different account conditions.

5. **Integration Testing:** Separate components allow the team to verify how the Controller, account management, and transaction processing work together.

6. **Path and Data-Flow Testing:** Smaller functions make it easier to examine execution paths and track how transaction data moves through the application.

Overall, the modular design makes defects easier to identify and allows more focused and organized testing.

#### 3.2.3 Weaknesses

Despite these improvements, Solution 2 still has some limitations:

1. **Increased Complexity:** More components and classes require additional planning and development effort.

2. **Integration Challenges:** Separate components must communicate correctly, requiring additional integration testing.

3. **Development Time:** Implementing and testing multiple components may take longer than the simpler design.

4. **State Management:** Additional account states require clearly defined rules to prevent inconsistent behaviour.

5. **Transaction Consistency:** Transfers must update both affected accounts correctly to prevent inaccurate balances if an operation fails.

Although Solution 2 improves testability and maintainability, further refinement and testing will be necessary before selecting and implementing the final solution.
