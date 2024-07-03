# ATM-Operations-Program
### This project, "Simple ATM Simulator," is a basic simulation of an ATM machine that allows users to perform essential banking operations such as checking their balance, withdrawing money, and depositing money. The program ensures secure access by requiring the user to enter a correct PIN before any transaction.
## Here is an explanation of each part of the ATM program:

## python

print("Welcome to ABC Bank ATM")
ATM_Pin = 1234
Balance = 50000
Chances = 3

## Welcome Message and Variable Initialization:

print("Welcome to ABC Bank ATM"): This line displays a welcome message to the user.
ATM_Pin = 1234: This sets the ATM PIN to 1234.
Balance = 50000: This sets the initial balance to 50,000.
Chances = 3: This sets the number of attempts the user has to enter the correct PIN to 3.
    while Chances != 0:
       user_pin = int(input("Please enter your four-digit PIN: "))    
## PIN Entry and Validation Loop:
## while Chances != 0: This starts a loop that continues as long as the user has remaining chances.
## user_pin = int(input("Please enter your four-digit PIN: ")):
## This prompts the user to enter their four-digit PIN and converts the input to an integer.

if user_pin != ATM_Pin:
     Chances -= 1
      print("You have entered the wrong PIN. Please enter the correct PIN to proceed.")
      print(f"You have {Chances} chances left.")
      
## Incorrect PIN Handling:
## if user_pin != ATM_Pin: This checks if the entered PIN is incorrect.
## Chances -= 1: This decreases the number of remaining attempts by 1.
## print("You have entered the wrong PIN. Please enter the correct PIN to proceed."): 

## This informs the user that the entered PIN is incorrect.
print(f"You have {Chances} chances left."): This displays the number of remaining attempts.
   else:
       while True:
           user_choice = input("B: Balance, W: Withdraw, D: Deposit: ")
## Correct PIN Handling and Transaction Menu:
## else: This block executes if the entered PIN is correct.
## while True: This starts a loop for performing transactions.
## user_choice = input("B: Balance, W: Withdraw, D: Deposit: ").upper(): This prompts the user to choose an action (Balance, Withdraw, Deposit) and converts the input to uppercase for consistency.

            if user_choice == 'B':
                print(f"Your total balance is ${Balance}")
                
## Balance Inquiry:
## if user_choice == 'B': This checks if the user chose to check the balance.
## print(f"Your total balance is ${Balance}"): This displays the current balance.

            elif user_choice == 'W':
                user_withdrawn = int(input("Enter the amount you want to withdraw: "))
                if user_withdrawn <= Balance:
                    Balance -= user_withdrawn
                    print(f"Your current total balance is ${Balance}")
                else:
                    print("Insufficient funds.")
                    
## Withdraw Money:
## elif user_choice == 'W': This checks if the user chose to withdraw money.
## user_withdrawn = int(input("Enter the amount you want to withdraw: ")): This prompts the user to enter the amount to withdraw and converts it to an integer.
## if user_withdrawn <= Balance: This checks if the withdrawal amount is less than or equal to the current balance.
## Balance -= user_withdrawn: This deducts the withdrawal amount from the balance.
## print(f"Your current total balance is ${Balance}"): This displays the updated balance.
## else: This block executes if the withdrawal amount is greater than the current balance.
## print("Insufficient funds."): This informs the user that they have insufficient funds.

            elif user_choice == 'D':
                user_deposit = int(input("Enter the amount you want to deposit in your A/C: "))
                Balance += user_deposit
                print(f"Your current total balance is ${Balance}")
                
## Deposit Money:
## elif user_choice == 'D': This checks if the user chose to deposit money.
## user_deposit = int(input("Enter the amount you want to deposit in your A/C: ")): This prompts the user to enter the amount to deposit and converts it to an integer.
## Balance += user_deposit: This adds the deposit amount to the balance.
## print(f"Your current total balance is ${Balance}"): This displays the updated balance.

            else:
                print("Invalid choice. Please choose a valid option.")
                continue
                
## Invalid Choice Handling:
## else: This block executes if the user enters an invalid choice.
## print("Invalid choice. Please choose a valid option."): This informs the user that they have made an invalid choice.
## continue: This restarts the loop to prompt the user again.

            user_exit = input("Do you want to continue the transaction? YES/NO: ").upper()
            if user_exit == "NO":
                print("Thank you for using this ATM. Have a nice day!")
                break
        break
        
## Transaction Continuation Prompt:
## user_exit = input("Do you want to continue the transaction? YES/NO: ").upper(): This prompts the user to decide whether to continue the transaction and converts the input to uppercase.
## if user_exit == "NO": This checks if the user chose not to continue.
## print("Thank you for using this ATM. Have a nice day!"): This displays a thank-you message.
## break: This exits the transaction loop.
## break: This exits the PIN entry loop.

if Chances == 0:
    print("You have entered the wrong PIN too many times. Your account is locked.")
    
## Account Locking After Too Many Incorrect Attempts:
## if Chances == 0: This checks if the user has used all their attempts.
## print("You have entered the wrong PIN too many times. Your account is locked."): This informs the user that their account is locked due to too many incorrect PIN entries.
## This program provides a simple ATM simulation where users can check their balance, withdraw money, and deposit money after entering the correct PIN.
