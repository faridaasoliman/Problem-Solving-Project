Account Number Generation:
	•	Unique account numbers for new customer accounts are generated using an incremental approach. A global variable (lastAccountId) is initialized with a starting value (e.g., 1000). Each time a new account is created in the new_acc() function, lastAccountId is incremented, and the incremented value is assigned as the account number for the new account. This ensures that each account receives a unique identifier.
	2.	Random Number Generation for Credit Card Numbers:
	•	When customers apply for new credit cards, random card numbers are generated for them using the rand() function provided by the C standard library. The rand() function generates pseudo-random numbers, and to ensure uniqueness, the generated numbers are typically combined with other factors such as timestamps or unique identifiers. In this project, the card number generation logic might involve generating a random number within a certain range and associating it with the customer’s account.
Of course! Let's provide answers to the questions generated earlier about the bank management system project:

1. **Project Overview:**
   - The bank management system project aims to provide a software solution for managing customer accounts, transactions, credit card services, and related banking functionalities. It facilitates various banking operations, such as account creation, fund transfers, credit card applications, balance inquiries, and statement generation.

2. **Functionality:**
   - The system allows users to create new accounts by providing personal details and an initial deposit.
   - Users can perform transactions, including deposits and withdrawals, to manage their account balances.
   - Fund transfer functionality enables customers to transfer money between their accounts or to other accounts within the bank.
   - Customers can apply for credit cards, which are assigned unique card numbers, and make payments towards their credit card balances.
   - The system provides options to view customer profiles, including account details, balances, and credit card information.
   - Bank statements can be generated to provide transaction histories and account summaries.
   - Customers can also request account deletion if needed.

3. **Account Management:**
   - Unique account numbers are generated for new accounts using an incremental approach, where each account is assigned a unique identifier starting from a predefined value (e.g., 1000).
   - Error handling and validation checks are implemented during account creation and transaction processing to ensure data integrity and prevent invalid inputs.


5. **Error Handling and Security:**
   - The system incorporates error-handling mechanisms to address invalid inputs, runtime errors, and exceptional scenarios gracefully.
   - Security measures include data encryption, access controls, and secure storage practices to protect customer data and transactions from unauthorized access or manipulation.

6. **Currency Conversion Feature:**
   - Currency conversion functionality allows users to convert amounts between different currencies using predefined exchange rates relative to USD.
   - Exchange rates and currency codes are stored in arrays within the system, and user input is validated to ensure accurate conversions.

7. **Scalability and Maintenance:**
   - The system is designed to handle a significant number of customers and accounts, with scalability considerations taken into account during the development process.
   - Code maintainability is facilitated through well-organized code structures, documentation practices, and adherence to coding standards.

8. **Testing and Validation:**
   - The system undergoes rigorous testing using various methodologies, including unit testing, integration testing, and user acceptance testing.
   - Test cases cover critical functionalities and edge cases to validate system behavior and ensure reliability.
  



Here is a detailed explanation of the functionality of the provided bank management system code, broken down into key points:

### 1. **Structures Defined**
   - **Customer**: Represents a customer with fields for personal information, account details, transactions, and loans.
     - `id`: Unique account number.
     - `name`: Customer's name.
     - `dob`: Date of birth.
     - `address`: Customer's address.
     - `phone`: Phone number.
     - `balance`: Account balance.
     - `accountType`: Type of account (e.g., saving, current).
     - `cardNumber`: Credit card number.
     - `password`: Account password.
     - `creditCardBalance`: Balance on the credit card.
     - `transactions`: Array of transactions related to the account.
     - `numTransactions`: Number of transactions.
     - `loans`: Array of loans associated with the customer.
     - `numLoans`: Number of loans.
   - **Transaction**: Represents a financial transaction.
     - `date`: Date of the transaction.
     - `type`: Type of transaction (e.g., deposit, withdrawal).
     - `amount`: Amount involved in the transaction.
   - **Loan**: Represents a loan taken by a customer.
     - `accountNumber`: Account number associated with the loan.
     - `amount`: Loan amount.
     - `annualInterestRate`: Annual interest rate of the loan.
     - `durationMonths`: Duration of the loan in months.
     - `monthlyPayment`: Monthly payment amount.
     - `remainingBalance`: Remaining balance of the loan.

### 2. **Global Variables**
   - `customers[MAX_CUSTOMERS]`: Array to store all customer records.
   - `numCustomers`: Counter to keep track of the number of customers.
   - `lastAccountId`: Stores the last assigned account ID (initialized to 1000).

### 3. **Function Implementations**
   - **main()**: The entry point of the program.
     - Welcomes the user.
     - Asks if the user already has an account.
     - Calls `authenticate()` if the user has an account, or `new_acc()` to create a new account.

   - **authenticate()**: Handles user authentication.
     - Prompts for account number and password.
     - Verifies credentials by checking against stored customer data.
     - Calls `menu()` if authentication is successful.

   - **new_acc()**: Creates a new customer account.
     - Prompts for customer details (name, DOB, address, phone, initial deposit, account type, password).
     - Assigns a unique ID to the new account.
     - Initializes `numLoans` to 0.
     - Adds the new customer to the `customers` array.
     - Calls `menu()` after account creation.

   - **menu()**: Displays the main menu and handles user choices.
     - Lists various options like changing account details, making transactions, transferring funds, etc.
     - Calls corresponding functions based on user input.

   - **transact()**: Handles deposits and withdrawals.
     - Prompts for account number and transaction type.
     - Updates the account balance based on the transaction type.
     - Records the transaction details.

   - **transfer()**: Manages fund transfers between accounts.
     - Prompts for sender and receiver account numbers.
     - Verifies both accounts and updates balances accordingly.

   - **apply_for_loan()**: Processes loan applications.
     - Prompts for account number, loan amount, interest rate, and duration.
     - Adds loan details to the customer's record if the loan limit is not exceeded.

   - **pay_loan()**: Manages loan repayments.
     - Prompts for account number and loan repayment details.
     - Updates the loan balance based on the repayment amount.

   - **apply_for_card()**: Handles credit card applications.
     - Prompts for account number.
     - Assigns a new credit card number and initializes the balance to zero.

   - **pay_ur_credit_card()**: Processes credit card payments.
     - Prompts for account number and payment amount.
     - Updates the credit card balance.

   - **view_profile()**: Displays customer profile details.
     - Prompts for account number.
     - Prints account information like name, DOB, address, balance, etc.

   - **bank_statement()**: Generates a bank statement for a customer.
     - Prompts for account number.
     - Prints all transactions related to the account.

   - **erase()**: Deletes a customer account.
     - Prompts for account number.
     - Removes the account from the `customers` array.

   - **currency_converter_option()**: Handles currency conversion.
     - Prompts for the amount and the currencies to convert from and to.
     - Uses predefined exchange rates to perform the conversion.

### 4. **Utility Functions**
   - **change_account_details()**: Updates the customer's address and phone number.
     - Prompts for account number and new details.
     - Updates the customer record accordingly.

### 5. **General Flow**
   - The program starts by either authenticating an existing user or creating a new account.
   - Once authenticated, the user is presented with a menu to perform various banking operations.
   - Each menu option corresponds to a specific function that handles the required task.
   - The program keeps track of customers, transactions, and loans using arrays and updates them based on user actions.

This structured approach ensures that all functionalities are encapsulated within their respective functions, making the code modular and easier to manage.


9. **Project Implementation Details:**
    - The project is implemented using a programming language such as C, with a modular structure and separation of concerns to facilitate maintainability and extensibility.
    - Design patterns and best practices are followed to ensure code quality, readability, and scalability.
