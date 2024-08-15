# ATM-Project
class ATM: 
    def __init__(self): 
        self.pin = 2280
        self.balance = 2000
        self.menu()
    def menu(self):
        print("""
              What would you like to do today?
              1. Generate_pin
              2. Change_pin
              3. Check_balance
              4. Withdraw
              5. Deposit
              6. Exit
              """)
        option = int(input("Enter your choice: "))
        #Check Balance#
        if option == 3:
            self.Check_balance()
        #Withdraw balance#
        elif option == 4:
            self.Withdraw()
        #Deposit balance#
        elif option == 5:
            self.Depoist()
        #Exit#
        elif option == 6:
            sys.exit()
    def Check_balance(self):
            input_pin = int(input("Enter your pin: "))
            if input_pin == self.pin:
                print(f"your balance is {self.balance}")
            else:
                print("Invalid pin")
            self.menu()
    #Withdraw#
    def Withdraw(self):
        input_pin = int(input("Enter your pin: "))
        if input_pin == self.pin:
            input_balance = int(input("Enter the amount you would like to withdraw: "))
            if input_balance <= self.balance:
                self.balance = self.balance - input_balance
                print(f"Your new balance is {self.balance}")
            else:
                print("You don't have enough money:)")
        else: 
            print("Your pin is incorrect")
        self.menu()
#Depoist#
    def Depoist(self):
        input_pin = int(input("Enter your pin: "))
        if input_pin == self.pin:
            input_deposit = int(input("Enter the amount you would like to deposit:"))
            self.balance = self.balance + input_deposit
            print(f"Your new balance is {self.balance}")
        else:
           print("Your pin is incorrect")
        self.menu()
        
        
sbi = ATM()
