# vaultflow
# project: vault flow
## Section A (Account Hierarchy):
- Account (Abstract base): holds accountNumber, balance, and an abstract applyMonthlyFee() or calculateInterest() method.
- SavingsAccount (Subclass): adds an interest rate, minimum balance rule, and concrete interest calculation.
- CheckingAccount (Subclass): adds an overdraft limit and overrides withdrawal behavior to permit negative balances down to that limit.
## Section B (Transaction Hierarchy):
- Transaction (Abstract base): holds transactionId, amount, timestamp, and an abstract execute(Account account) method.
- DepositTransaction (Subclass): implements execute() to validate and deposit funds into any Account.
- WithdrawalTransaction (Subclass): implements execute() to attempt a withdrawal, handling success or failure gracefully depending on the account's rules.
