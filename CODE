import java.util.ArrayList;
import java.util.Scanner;

public class Bank {

    static ArrayList<Integer> accountNumbers = new ArrayList<>();
    static ArrayList<String> accountNames = new ArrayList<>();
    static ArrayList<Double> accountBalances = new ArrayList<>();

    // shared scanner used by all modules to read user input
    static Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        System.out.println("Welcome to the Bank Management System!");

        // Menu loop keeps running until the user chooses to exit (option 6)
        int choice = 0;
        while (choice != 6) {
            System.out.println();
            System.out.println("1. Create Account");
            System.out.println("2. Deposit Money");
            System.out.println("3. Withdraw Money");
            System.out.println("4. Check Balance");
            System.out.println("5. Show All Accounts");
            System.out.println("6. Exit");
            System.out.print("Enter your choice: ");

            // Read the user's choice and convert it from String to integer
            choice = Integer.parseInt(scanner.nextLine());

            if (choice == 1) {
                //Account Management
                createAccount();
            } else if (choice == 2) {
                // Deposit Money in the accuont
                depositMoney();
            } else if (choice == 3) {
                // Withdraw Money in the accuont
                withdrawMoney();
            } else if (choice == 4) {
                // Check the current balance in the account
                checkBalance();
            } else if (choice == 5) {
                // Shows all the accounts in the bank along with their details
                showAllAccounts();
            } else if (choice == 6) {
                System.out.println("Thank you for using the Bank Management System.");
            } else {
                // Shows invalid answer for any number outside the valid menu range 
                System.out.println("Invalid choice. Please try again.");
            }
        }
    }

    // Searches for an account number and returns its position in the Array
    static int findAccount(int accNumber) {
        for (int i = 0; i < accountNumbers.size(); i++) {
            if (accountNumbers.get(i) == accNumber) {
                return i;
            }
        }
        return -1;
    }

    // MODULE 1
    // Creates a new bank account
    static void createAccount() {
        System.out.print("Enter account number: ");
        int accNumber = Integer.parseInt(scanner.nextLine());

         // Check whether the account already exists 
        if (findAccount(accNumber) != -1) {
            System.out.println("Account already exists.");
            return;
        }

        System.out.print("Enter account holder name: ");
        String name = scanner.nextLine();

        System.out.print("Enter initial deposit: ");
        double amount = Double.parseDouble(scanner.nextLine());

        // Add the new account details to their positions
        accountNumbers.add(accNumber);
        accountNames.add(name);
        accountBalances.add(amount);

        System.out.println("Account created successfully.");
    }

    // MODULE 2
    // Deposits money into existing account
    static void depositMoney() {
        System.out.print("Enter account number: ");
        int accNumber = Integer.parseInt(scanner.nextLine());
        int index = findAccount(accNumber);

        if (index == -1) {
            System.out.println("Account not found.");
            return;
        }

        System.out.print("Enter amount to deposit: ");
        double amount = Double.parseDouble(scanner.nextLine());

        double newBalance = accountBalances.get(index) + amount;
        accountBalances.set(index, newBalance);

        System.out.println("Deposit successful. New balance: " + newBalance);
    }

    // Withdraws money from existing account
    static void withdrawMoney() {
        System.out.print("Enter account number: ");
        int accNumber = Integer.parseInt(scanner.nextLine());
        int index = findAccount(accNumber);

        if (index == -1) {
            System.out.println("Account not found.");
            return;
        }

        System.out.print("Enter amount to withdraw: ");
        double amount = Double.parseDouble(scanner.nextLine());

        double currentBalance = accountBalances.get(index);
        if (amount > currentBalance) {
            System.out.println("Insufficient balance.");
            return;
        }

        double newBalance = currentBalance - amount;
        accountBalances.set(index, newBalance);

        System.out.println("Withdrawal successful. New balance: " + newBalance);
    }

    // MODULE 3
    // Displays the current bank balance of an account
    static void checkBalance() {
        System.out.print("Enter account number: ");
        int accNumber = Integer.parseInt(scanner.nextLine());
        int index = findAccount(accNumber);

        if (index == -1) {
            System.out.println("Account not found.");
            return;
        }

        System.out.println("Current balance: " + accountBalances.get(index));
    }

    // Displays the details of all the accounts in the bank
    static void showAllAccounts() {
        if (accountNumbers.isEmpty()) {
            System.out.println("No accounts found.");
            return;
        }

        System.out.println("\n--- All Accounts ---");
        for (int i = 0; i < accountNumbers.size(); i++) {
            // Display the account number
            System.out.println("Account Number: " + accountNumbers.get(i));

            // Display the account holder's name
            System.out.println("Name: " + accountNames.get(i));

             // Display the balance
            System.out.println("Balance: " + accountBalances.get(i));
            System.out.println("---------------------");
        }
    }
}
