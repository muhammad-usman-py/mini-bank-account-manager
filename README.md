# 🏦 Bank Account Management System

A simple Python program simulating basic bank account operations such as deposit, withdrawal, and displaying account info. It uses constructors and methods in a class to encapsulate account behavior.

---

## ✨ Features

- 👤 Create a bank account with holder's name and a valid 12 or 14-digit IBAN/account number.
- 🎲 Initial random balance assigned on account creation.
- 💰 Deposit money to the account.
- 💸 Withdraw money with balance validation.
- 🖥️ Interactive console interface for transactions.

---

## 🧑‍💻 Code Overview

```python
from random import randint

class Bankaccount:
    def __init__(self):
        self.name = input("Enter Bank Holder Name:\n")
        while True:
            self.acc_number = (input("Enter Your 12 or 14-digit IBAN or account Number:\n"))
            if len(self.acc_number) != 12 and len(self.acc_number) != 14:
                print("Invalid account Number")
                continue
            else:
                break
        self.initial_Balance = randint(0, 500)

    def info(self):
        print(
            f"Account Holder Name: {self.name}\nAccount Number: {self.acc_number}\nInitial Balance: {self.initial_Balance}")

    def deposit(self):
        amt = int(input("Enter the amount you want to deposit:\n"))
        if amt > 0:
            print(f"{amt}Rs. depositted to your account {self.acc_number}")
            self.initial_Balance = self.initial_Balance + amt
            print(f"Your new balance is: {self.initial_Balance}")

    def withdraw(self):
        amt = int(input("Enter the amount you want to withdraw:\n"))
        if amt > 0 and amt <= self.initial_Balance:
            print(f"{amt}Rs. withdrawn from your account {self.acc_number}")
            self.initial_Balance -= amt
            print(f"Your new balance is: {self.initial_Balance}")
        else:
            print("Invalid amount")

Meezan = Bankaccount()
Meezan.info()

print("-" * 40)
while True:
    choice = input(
        "Enter 'D' to deposit amount\nEnter 'W' to withdraw amount\nEnter 'E' to exit:\n").strip().upper()
    if choice == 'D':
        Meezan.deposit()
    elif choice == 'W':
        Meezan.withdraw()
    elif choice == 'E':
        print("Thank you for using our banking services!")
        break
    else:
        print("Invalid choice. Please choose a valid option.")

    again = input("Do you want to make another transaction? Enter yes/no:\n").strip().lower()
    if again != 'no':
        continue
    else:
        print("Thanks for using our banking services!")
        break
```

## 🚀 Usage

- Run the program.
- Enter the bank holder name.
- Enter a valid 12 or 14-digit account number.
- Use the interactive menu to deposit or withdraw money.
- Exit the program by choosing `'E'`.

---

## 📝 Notes

- The initial balance is randomly assigned between 0 and 500.
- Only valid deposit and withdrawal amounts are accepted.
- The program will keep prompting for transactions until the user exits.
