## Bank Management System

A simple command-line Bank Management System written in Java. It lets a
user creates account, deposit and withdraw money, check balance and view
all accounts — all through a terminal menu, with no database or GUI required.

## Overview

This project simulates the core operations of a bank's system.
All data is kept in memory for the duration of a single run (nothing is
saved to disk), which keeps the project dependency-free and fully runnable
from the command line. It is built as three cooperating modules (Account
Management, Transaction Processing, and Reporting) driven by a single menu
loop in `Bank.java`.

## Features

- Create a new account with an account number, holder name, and initial deposit
- Deposit money into an existing account
- Withdraw money from an existing account (blocked if funds are insufficient)
- Check the balance of a single account
- View a list of all accounts and their balances
- Input validation for duplicate accounts, missing accounts, and
  insufficient balance
- Menu-driven loop that keeps running until the user chooses to exit

## Technologies / Tools Used

- **Language:** Java (Java only — no external libraries or frameworks)
- **Build tool:** Java Development Kit (JDK) command-line tools (`javac`, `java`)
- **Interface:** Command-line / terminal (text-based menu)
- **Storage:** For memory (`ArrayList`) — no database or file storage required

## Project Structure

```
BankManagementSystem/
├── Main.java              # Entry point, menu loop, and workflow routing
├── AccountManager.java    # Module 1: Account Management
├── TransactionManager.java# Module 2: Transaction Processing
├── ReportManager.java     # Module 3: Reporting / Inquiry
├── README.md
├── statement.md
└── PROJECT_REPORT.md
```

## Prerequisites

- A Java Development Kit (JDK), version 8 or later, installed on your machine.
  - Check with: `java -version` and `javac -version`
  - If not installed, download it from
    [Oracle JDK](https://www.oracle.com/java/technologies/downloads/) or
    install the free [OpenJDK](https://openjdk.org/) (e.g. via
    `sudo apt install openjdk-21-jdk` on Ubuntu/Debian, or
    `brew install openjdk` on macOS).
- A terminal / command prompt.
- No other dependencies, packages, or configuration files are required.

## Setup & Installation

1. **Get the project files.**
   Clone the repository, or download and extract the ZIP:
   ```bash
   git clone <your-repository-url>
   cd BankManagementSystem
   ```

2. **Verify Java is installed.**
   ```bash
   java -version
   javac -version
   ```
   Both commands should print a version number. If either fails, install a
   JDK first (see Prerequisites above).

## Running the Project

1. **Compile all Java files** (run from inside the project folder, the same
   folder that contains `Main.java`):
   ```bash
   javac *.java
   ```
   This creates `.class` files for `Main`, `AccountManager`,
   `TransactionManager`, and `ReportManager` in the same folder.

2. **Run the program:**
   ```bash
   java Main
   ```

3. **Use the menu.** You will see:
   ```
   Welcome to the Bank Management System!

   1. Create Account
   2. Deposit Money
   3. Withdraw Money
   4. Check Balance
   5. Show All Accounts
   6. Exit
   Enter your choice:
   ```
   Type a number (1–6) and press Enter, then follow the prompts for that
   option (account number, name, amount, etc.).

4. **Exit** by choosing option `6` at any time.

## Instructions for Testing

No testing framework is required — the program is verified manually by
running it and exercising each module through the menu:

1. Compile and run the program as described above.
2. **Test account creation (Module 1):**
   - Choose `1`, create an account (e.g. number `101`, name `Alice`, deposit `500`).
   - Choose `1` again with the **same** account number `101` — it should say
     "Account already exists."
3. **Test transactions (Module 2):**
   - Choose `2`, deposit `200` into account `101` — balance should become `700`.
   - Choose `3`, withdraw `1000` from account `101` — it should say
     "Insufficient balance."
   - Choose `3`, withdraw `200` from account `101` — balance should become `500`.
4. **Test reporting (Module 3):**
   - Choose `4`, check the balance of account `101` — it should print the
     current balance.
   - Choose `5` to list all accounts and confirm the details are correct.
5. **Test invalid input handling:**
   - Try option `4` or `1` with an account number that was never created —
     it should say "Account not found."
   - Enter an out-of-range menu choice (e.g. `9`) — it should say
     "Invalid choice. Please try again."
6. Choose `6` to exit and confirm the program terminates cleanly.

Since all data is stored in memory, restarting the program (`java Main`)
always begins with zero accounts — this is expected behavior, not a bug.
