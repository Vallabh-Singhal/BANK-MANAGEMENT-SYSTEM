## Project Statement
 
Manual, paper-based or spreadsheet-based tracking of bank accounts is slow,
error-prone, and hard to audit. Simple operations like opening an account,
depositing or withdrawing funds, checking a balance. This project addresses that
need with a lightweight, command-line Bank Management System that performs
these core operations correctly and predictably.
 
## Scope of the Project
 
**Current features:**
- Creating new bank accounts with a unique account number, account holder name and
  initial deposit.
- Depositing funds into an existing account.
- Withdrawing funds from an existing account, with a balance check to prevent wrong balance.
- Checking the current balance of an account.
- Displaying a report of all accounts held in the system.
- Basic input validation (duplicate accounts, missing accounts,
  insufficient funds, invalid menu choices).
  
**Future scope:**
- Persistent storage (a database or file-based save/load) — all data exists
  only for the duration of one program run.
- User authentication, login, or multi-user access control.
- A graphical user interface (GUI) or web interface — the system is
  command-line only, by design.
- Interest calculation, loans, or other advanced banking products.
- Multi-currency support.
  
## Target Users

- **Students / evaluators** reviewing the project as a demonstration of
  core Java programming, modular design, and command-line application
  structure.
- **Small-scale learners or hobbyists** who want a simple, self-contained
  example of how a bank's basic operations can be modeled in code.
- **Instructors** assessing understanding of functional decomposition
  (splitting a system into modules), input/output handling, and control
  flow in a menu-driven application.
  
## High-Level Features
 
1. **Account Management** — create and find accounts.
2. **Transaction Processing** — deposit and withdraw money from an
   existing account.
3. **Reporting / Inquiry** — check a single balance or list every account
   in the system.
4. **Menu-Driven Workflow** — a continuous command-line loop that lets the
   user repeat any operation until they choose to exit.
5. **Valid Input** — guards against duplicate accounts, unknown
   accounts, insufficient funds, and invalid menu selections.
